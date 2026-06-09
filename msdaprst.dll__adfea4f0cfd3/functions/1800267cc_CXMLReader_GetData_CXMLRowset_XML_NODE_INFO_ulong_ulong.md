# CXMLReader::GetData(CXMLRowset *,_XML_NODE_INFO * *,ulong *,ulong)

- ea: `0x1800267cc`
- end: `0x180026a94`
- name: `?GetData@CXMLReader@@QEAAJPEAVCXMLRowset@@PEAPEAU_XML_NODE_INFO@@PEAKK@Z`
- size: `712`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CXMLRowset *, struct _XML_NODE_INFO **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x1800263a4`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x1800267cc`
- `0x180028148`
- `0x180029dc0`
- `0x18002f092`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002694b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180026971`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800269a0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002694b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180026971`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800269a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800269d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800269f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180026a08`
- `OLEAUT32!__imp_SysFreeString` at `0x1800269d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800269f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180026a08`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CXMLReader::GetData(
        CCollectionList **this,
        struct CXMLRowset *a2,
        struct _XML_NODE_INFO **a3,
        unsigned int *a4,
        unsigned int a5)
{
  CCollectionList **v5; // rdi
  const OLECHAR *v6; // rsi
  __int64 v7; // r10
  int v8; // edx
  OLECHAR *v9; // rbx
  UINT v10; // ecx
  struct _XML_NODE_INFO **v11; // r14
  unsigned int v12; // r13d
  struct _XML_NODE_INFO **v13; // r15
  unsigned int v14; // r12d
  struct _XML_NODE_INFO *v15; // rax
  unsigned __int128 v16; // rax
  unsigned __int8 *v17; // rax
  unsigned __int8 *v19; // rcx
  unsigned __int8 *v20; // r12
  struct _XML_NODE_INFO *v21; // rdi
  char v22; // r15
  int v23; // eax
  int v24; // ecx
  OLECHAR *v25; // rdi
  char v26; // r13
  unsigned __int16 *v27; // r14
  OLECHAR *v28; // rsi
  unsigned __int16 *v29; // r15
  __int64 v30; // rax
  __int64 v31; // rdx
  UINT ui; // [rsp+30h] [rbp-28h]
  __int64 v33; // [rsp+38h] [rbp-20h]
  unsigned __int64 v34; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int8 *v35; // [rsp+48h] [rbp-10h]
  unsigned __int8 *v38; // [rsp+B0h] [rbp+58h]

  v5 = this;
  v6 = 0;
  v34 = 0;
  v7 = (__int64)*a3;
  v33 = (__int64)*a3;
  v8 = *a4;
  v9 = 0;
  v35 = 0;
  v10 = 0;
  ui = 0;
  v11 = a3 + 1;
  v12 = v8 + 1;
  v13 = a3 + 1;
  v14 = 1;
  if ( v8 + 1 < a5 )
  {
    do
    {
      v15 = *v13;
      if ( !*v13 )
        break;
      if ( *((_DWORD *)v15 + 1) != 13 )
        break;
      v10 += *((_DWORD *)v15 + 6);
      ++v13;
      ++v12;
    }
    while ( v12 < a5 );
    ui = v10;
  }
  if ( v12 - v8 == 1 )
  {
    v6 = (const OLECHAR *)&wszZls;
    goto LABEL_19;
  }
  if ( v12 - v8 == 2 )
  {
    v6 = (const OLECHAR *)*((_QWORD *)*v11 + 2);
LABEL_19:
    v22 = 0;
    goto LABEL_20;
  }
  v16 = (v10 + 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v10 + 1, 2u) )
    LODWORD(v16) = -1;
  v17 = MMMAlloc(v16, DWORD2(v16));
  v9 = (OLECHAR *)v17;
  v35 = v17;
  if ( !v17 )
  {
    operator delete(0);
    return 2147942414LL;
  }
  v19 = v17;
  if ( v11 < v13 )
  {
    v20 = v17;
    do
    {
      v21 = *v11;
      memcpy_0(v20, *((const void **)*v11 + 2), 2LL * *((unsigned int *)*v11 + 6));
      v20 += 2 * *((unsigned int *)v21 + 6);
      ++v11;
    }
    while ( v11 < v13 );
    v38 = v20;
    v14 = 1;
    v19 = v38;
    v5 = this;
  }
  *(_WORD *)v19 = 0;
  v22 = 1;
  v7 = v33;
LABEL_20:
  v23 = CCollectionList::LookUpByKey(
          (struct CXMLRowset *)((char *)a2 + 552),
          *(unsigned __int16 **)(v7 + 16),
          *(_DWORD *)(v7 + 24),
          &v34);
  v24 = *((_DWORD *)v5 + 119);
  if ( !v23 )
  {
    if ( ((v24 - 4) & 0xFFFFFFFB) != 0 )
      v30 = *((_QWORD *)a2 + 35);
    else
      v30 = *((_QWORD *)a2 + 36);
    v31 = *(_QWORD *)(v30 + 8LL * (unsigned int)v34);
    *(_QWORD *)v31 = ui;
    if ( v22 )
    {
      v6 = v9;
      v9 = 0;
      *(_DWORD *)(v31 + 4) = 0x1000000;
    }
    *(_QWORD *)(v31 + 8) = v6;
    *a4 = v12 - 1;
    goto LABEL_36;
  }
  if ( v24 == 1 )
  {
    v5[17] = (CCollectionList *)*((_QWORD *)a2 + 79);
    if ( v22 )
    {
      v25 = SysAllocStringLen(v9, ui);
      v26 = 1;
      v27 = v25;
      v28 = v25;
    }
    else
    {
      v27 = SysAllocStringLen(v6, ui);
      v28 = v27;
      v26 = 2;
      v25 = v27;
    }
    v29 = SysAllocStringLen(*(const OLECHAR **)(v33 + 16), *(_DWORD *)(v33 + 24));
    v34 = (unsigned __int64)v29;
    CXMLReader::ProcessRowsetAttribute(this, *(_DWORD *)(v33 + 28), v29, v27, a2);
    SysFreeString(v29);
    if ( (v26 & 2) != 0 )
    {
      v26 &= ~2u;
      SysFreeString(v28);
    }
    if ( (v26 & 1) != 0 )
      SysFreeString(v25);
    this[17] = (CCollectionList *)*((_QWORD *)this[17] + 6);
LABEL_36:
    v14 = 0;
  }
  operator delete((unsigned __int8 *)v9);
  return v14;
}

```

## disassembly

```asm
0x1800267cc  mov     [rsp-40h+bstrString], r9
0x1800267d1  mov     [rsp-40h+arg_8], rdx
0x1800267d6  mov     [rsp-40h+arg_0], rcx
0x1800267db  push    rbp
0x1800267dc  push    rbx
0x1800267dd  push    rsi
0x1800267de  push    rdi
0x1800267df  push    r12
0x1800267e1  push    r13
0x1800267e3  push    r14
0x1800267e5  push    r15
0x1800267e7  mov     rbp, rsp
0x1800267ea  sub     rsp, 58h
0x1800267ee  mov     rdi, rcx
0x1800267f1  xor     esi, esi
0x1800267f3  mov     dword ptr [rbp+arg_10], esi
0x1800267f6  mov     [rbp+var_18], rsi
0x1800267fa  mov     r10, [r8]
0x1800267fd  mov     [rbp+var_20], r10
0x180026801  mov     edx, [r9]; unsigned int
0x180026804  mov     ebx, esi
0x180026806  mov     [rbp+var_10], rbx
0x18002680a  mov     byte ptr [rbp+arg_10], sil
0x18002680e  mov     ecx, esi
0x180026810  mov     [rbp+ui], ecx
0x180026813  lea     r14, [r8+8]
0x180026817  lea     r13d, [rdx+1]
0x18002681b  mov     r15, r14
0x18002681e  lea     r12d, [rsi+1]
0x180026822  cmp     r13d, [rbp+arg_20]
0x180026826  jnb     short loc_180026849
0x180026828  mov     rax, [r15]
0x18002682b  test    rax, rax
0x18002682e  jz      short loc_180026846
0x180026830  cmp     dword ptr [rax+4], 0Dh
0x180026834  jnz     short loc_180026846
0x180026836  add     ecx, [rax+18h]
0x180026839  add     r15, 8
0x18002683d  add     r13d, r12d
0x180026840  cmp     r13d, [rbp+arg_20]
0x180026844  jb      short loc_180026828
0x180026846  mov     [rbp+ui], ecx
0x180026849  mov     eax, r13d
0x18002684c  sub     eax, edx
0x18002684e  sub     eax, r12d
0x180026851  jz      loc_1800268F4
0x180026857  cmp     eax, r12d
0x18002685a  jz      loc_1800268EB
0x180026860  inc     ecx
0x180026862  mov     eax, 2
0x180026867  mul     rcx
0x18002686a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180026871  cmovb   rax, rcx
0x180026875  mov     ecx, eax; unsigned int
0x180026877  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002687c  mov     rbx, rax
0x18002687f  mov     [rbp+var_10], rax
0x180026883  test    rax, rax
0x180026886  jnz     short loc_18002689A
0x180026888  mov     rcx, rax; void *
0x18002688b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026890  mov     eax, 8007000Eh
0x180026895  jmp     loc_180026A82
0x18002689a  mov     rcx, rax
0x18002689d  cmp     r14, r15
0x1800268a0  jnb     short loc_1800268DD
0x1800268a2  mov     r12, rax
0x1800268a5  mov     rdi, [r14]
0x1800268a8  mov     r8d, [rdi+18h]
0x1800268ac  add     r8, r8; Size
0x1800268af  mov     rdx, [rdi+10h]; Src
0x1800268b3  mov     rcx, r12; void *
0x1800268b6  call    memcpy_0
0x1800268bb  mov     eax, [rdi+18h]
0x1800268be  lea     r12, [r12+rax*2]
0x1800268c2  add     r14, 8
0x1800268c6  cmp     r14, r15
0x1800268c9  jb      short loc_1800268A5
0x1800268cb  mov     [rbp+arg_10], r12
0x1800268cf  mov     r12d, 1
0x1800268d5  mov     rcx, [rbp+arg_10]
0x1800268d9  mov     rdi, [rbp+arg_0]
0x1800268dd  xor     eax, eax
0x1800268df  mov     [rcx], ax
0x1800268e2  mov     r15b, r12b
0x1800268e5  mov     r10, [rbp+var_20]
0x1800268e9  jmp     short loc_1800268FF
0x1800268eb  mov     rax, [r14]
0x1800268ee  mov     rsi, [rax+10h]
0x1800268f2  jmp     short loc_1800268FB
0x1800268f4  lea     rsi, ?wszZls@@3PAGA; ushort near * wszZls
0x1800268fb  mov     r15b, byte ptr [rbp+arg_10]
0x1800268ff  mov     r14, [rbp+arg_8]
0x180026903  lea     rcx, [r14+228h]; this
0x18002690a  lea     r9, [rbp+var_18]; unsigned __int64 *
0x18002690e  mov     r8d, [r10+18h]; unsigned int
0x180026912  mov     rdx, [r10+10h]; unsigned __int16 *
0x180026916  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x18002691b  mov     ecx, [rdi+1DCh]
0x180026921  test    eax, eax
0x180026923  jz      loc_180026A28
0x180026929  cmp     ecx, r12d
0x18002692c  jnz     loc_180026A77
0x180026932  mov     rax, [r14+278h]
0x180026939  mov     [rdi+88h], rax
0x180026940  mov     edx, [rbp+ui]; ui
0x180026943  test    r15b, r15b
0x180026946  jz      short loc_18002696E
0x180026948  mov     rcx, rbx; strIn
0x18002694b  call    cs:__imp_SysAllocStringLen
0x180026952  nop     dword ptr [rax+rax+00h]
0x180026957  mov     rdi, rax
0x18002695a  mov     [rbp+bstrString], rax
0x18002695e  mov     r13d, r12d
0x180026961  mov     dword ptr [rbp+arg_10], r12d
0x180026965  mov     r14, rax
0x180026968  mov     rsi, [rbp+bstrString]
0x18002696c  jmp     short loc_180026995
0x18002696e  mov     rcx, rsi; strIn
0x180026971  call    cs:__imp_SysAllocStringLen
0x180026978  nop     dword ptr [rax+rax+00h]
0x18002697d  mov     r14, rax
0x180026980  mov     rsi, rax
0x180026983  mov     [rbp+bstrString], rax
0x180026987  mov     r13d, 2
0x18002698d  mov     dword ptr [rbp+arg_10], r13d
0x180026991  mov     rdi, [rbp+bstrString]
0x180026995  mov     rax, [rbp+var_20]
0x180026999  mov     edx, [rax+18h]; ui
0x18002699c  mov     rcx, [rax+10h]; strIn
0x1800269a0  call    cs:__imp_SysAllocStringLen
0x1800269a7  nop     dword ptr [rax+rax+00h]
0x1800269ac  mov     r15, rax
0x1800269af  mov     [rbp+var_18], rax
0x1800269b3  mov     rdx, [rbp+arg_8]
0x1800269b7  mov     [rsp+58h+var_38], rdx; struct CXMLRowset *
0x1800269bc  mov     r9, r14; unsigned __int16 *
0x1800269bf  mov     r8, rax; unsigned __int16 *
0x1800269c2  mov     rdx, [rbp+var_20]
0x1800269c6  mov     edx, [rdx+1Ch]; unsigned int
0x1800269c9  mov     r14, [rbp+arg_0]
0x1800269cd  mov     rcx, r14; this
0x1800269d0  call    ?ProcessRowsetAttribute@CXMLReader@@AEAAJKPEAG0PEAVCXMLRowset@@@Z; CXMLReader::ProcessRowsetAttribute(ulong,ushort *,ushort *,CXMLRowset *)
0x1800269d5  nop
0x1800269d6  mov     rcx, r15; bstrString
0x1800269d9  call    cs:__imp_SysFreeString
0x1800269e0  nop     dword ptr [rax+rax+00h]
0x1800269e5  nop
0x1800269e6  test    r13b, 2
0x1800269ea  jz      short loc_180026A00
0x1800269ec  and     r13d, 0FFFFFFFDh
0x1800269f0  mov     rcx, rsi; bstrString
0x1800269f3  call    cs:__imp_SysFreeString
0x1800269fa  nop     dword ptr [rax+rax+00h]
0x1800269ff  nop
0x180026a00  test    r12b, r13b
0x180026a03  jz      short loc_180026A14
0x180026a05  mov     rcx, rdi; bstrString
0x180026a08  call    cs:__imp_SysFreeString
0x180026a0f  nop     dword ptr [rax+rax+00h]
0x180026a14  mov     rax, [r14+88h]
0x180026a1b  mov     rcx, [rax+30h]
0x180026a1f  mov     [r14+88h], rcx
0x180026a26  jmp     short loc_180026A74
0x180026a28  lea     eax, [rcx-4]
0x180026a2b  mov     ecx, dword ptr [rbp+var_18]
0x180026a2e  test    eax, 0FFFFFFFBh
0x180026a33  jz      short loc_180026A3E
0x180026a35  mov     rax, [r14+118h]
0x180026a3c  jmp     short loc_180026A45
0x180026a3e  mov     rax, [r14+120h]
0x180026a45  mov     rdx, [rax+rcx*8]
0x180026a49  mov     eax, [rbp+ui]
0x180026a4c  mov     [rdx], eax
0x180026a4e  mov     dword ptr [rdx+4], 0
0x180026a55  test    r15b, r15b
0x180026a58  jz      short loc_180026A66
0x180026a5a  mov     rsi, rbx
0x180026a5d  xor     ebx, ebx
0x180026a5f  mov     dword ptr [rdx+4], 1000000h
0x180026a66  mov     [rdx+8], rsi
0x180026a6a  lea     eax, [r13-1]
0x180026a6e  mov     rcx, [rbp+bstrString]
0x180026a72  mov     [rcx], eax
0x180026a74  xor     r12d, r12d
0x180026a77  mov     rcx, rbx; void *
0x180026a7a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026a7f  mov     eax, r12d
0x180026a82  add     rsp, 58h
0x180026a86  pop     r15
0x180026a88  pop     r14
0x180026a8a  pop     r13
0x180026a8c  pop     r12
0x180026a8e  pop     rdi
0x180026a8f  pop     rsi
0x180026a90  pop     rbx
0x180026a91  pop     rbp
0x180026a92  retn
```
