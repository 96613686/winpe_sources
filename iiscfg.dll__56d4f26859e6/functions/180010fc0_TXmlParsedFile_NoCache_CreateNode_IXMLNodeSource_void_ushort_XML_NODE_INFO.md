# TXmlParsedFile_NoCache::CreateNode(IXMLNodeSource *,void *,ushort,_XML_NODE_INFO * *)

- ea: `0x180010fc0`
- end: `0x18001135b`
- name: `?CreateNode@TXmlParsedFile_NoCache@@EEAAJPEAUIXMLNodeSource@@PEAXGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `923`
- prototype: `__int64 __fastcall(TXmlParsedFile_NoCache *__hidden this, struct IXMLNodeSource *, void *, unsigned __int16, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001ef0`
- `0x180010ec4`
- `0x180010fc0`
- `0x18002e0b2`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800111d6`
- `ole32!CoTaskMemAlloc` at `0x18001123c`
- `ole32!CoTaskMemAlloc` at `0x1800111d6`
- `ole32!CoTaskMemAlloc` at `0x18001123c`

## pseudocode

```c
__int64 __fastcall TXmlParsedFile_NoCache::CreateNode(
        TXmlParsedFile_NoCache *this,
        struct IXMLNodeSource *a2,
        void *a3,
        unsigned __int16 a4,
        struct _XML_NODE_INFO **a5)
{
  struct _XML_NODE_INFO **v5; // r14
  int v7; // ecx
  unsigned __int64 v8; // r13
  __int64 v10; // rax
  struct _XML_NODE_INFO **v11; // rbx
  unsigned int v12; // ebp
  struct _XML_NODE_INFO *v13; // rax
  __int64 v14; // rcx
  struct _XML_NODE_INFO *v15; // rax
  __int64 v16; // r15
  __int64 v17; // r8
  struct _XML_NODE_INFO *v18; // rax
  __int64 v19; // rax
  bool v20; // cf
  SIZE_T v21; // rax
  _QWORD *v22; // rax
  struct _XML_NODE_INFO *v23; // rax
  struct _XML_NODE_INFO *v24; // rdi
  char *v25; // r15
  __int64 v26; // rcx
  struct _XML_NODE_INFO *v27; // rax
  __int64 v28; // rdi
  unsigned int v29; // ebx

  v5 = a5;
  v7 = *((_DWORD *)this + 12);
  v8 = a4;
  if ( !*((_DWORD *)*a5 + 3) )
    *((_DWORD *)this + 12) = v7 + 1;
  if ( !v7 )
    return 0;
  if ( *((_DWORD *)*v5 + 1) != 1 )
  {
    if ( *((_DWORD *)*v5 + 1) == 13 || *((_DWORD *)*v5 + 1) == 16 || *((_DWORD *)*v5 + 1) == 18 )
    {
      *(_DWORD *)(*((_QWORD *)this + 7) + 24LL) = *((_DWORD *)*v5 + 1);
      **((_DWORD **)this + 7) = v7;
      *(_DWORD *)(*((_QWORD *)this + 7) + 4LL) = *((_DWORD *)*v5 + 6);
      *(_QWORD *)(*((_QWORD *)this + 7) + 8LL) = *((_QWORD *)*v5 + 2) + 2LL * *((unsigned int *)*v5 + 7);
      *(_DWORD *)(*((_QWORD *)this + 7) + 20LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 7) + 16LL) = 0;
      return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 8) + 8LL))(
               *((_QWORD *)this + 8),
               *((_QWORD *)this + 7));
    }
    return 0;
  }
  if ( !*((_QWORD *)*v5 + 2) )
    return 0;
  v10 = *((_QWORD *)this + 7);
  v11 = 0;
  a5 = 0;
  v12 = 1;
  *(_DWORD *)(v10 + 24) = 1;
  **((_DWORD **)this + 7) = v7;
  *(_DWORD *)(*((_QWORD *)this + 7) + 4LL) = *((_DWORD *)*v5 + 6);
  *(_QWORD *)(*((_QWORD *)this + 7) + 8LL) = *((_QWORD *)*v5 + 2) + 2LL * *((unsigned int *)*v5 + 7);
  *(_DWORD *)(*((_QWORD *)this + 7) + 20LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 7) + 16LL) = 1;
  while ( v12 < (unsigned int)v8 )
  {
    v13 = v5[v12];
    if ( *((_DWORD *)v13 + 1) == 2 )
    {
      *(_DWORD *)(32 * (*(unsigned int *)(*((_QWORD *)this + 7) + 20LL) + 1LL) + *((_QWORD *)this + 7)) = *((_DWORD *)v13 + 6);
      v14 = v12 + 1;
      *(_QWORD *)(32LL * *(unsigned int *)(*((_QWORD *)this + 7) + 20LL) + *((_QWORD *)this + 7) + 40) = *((_QWORD *)v5[v12] + 2) + 2LL * *((unsigned int *)v5[v12] + 7);
      if ( (_DWORD)v14 == (_DWORD)v8 || (v15 = v5[v14], v16 = (unsigned int)v14, *((_DWORD *)v15 + 1) != 13) )
      {
        *(_DWORD *)(32LL * *(unsigned int *)(*((_QWORD *)this + 7) + 20LL) + *((_QWORD *)this + 7) + 48) = 0;
        *(_QWORD *)(32LL * *(unsigned int *)(*((_QWORD *)this + 7) + 20LL) + *((_QWORD *)this + 7) + 56) = 0;
      }
      else
      {
        ++v12;
        *(_DWORD *)(32LL * *(unsigned int *)(*((_QWORD *)this + 7) + 20LL) + *((_QWORD *)this + 7) + 48) = *((_DWORD *)v15 + 6);
        *(_QWORD *)(32LL * *(unsigned int *)(*((_QWORD *)this + 7) + 20LL) + *((_QWORD *)this + 7) + 56) = *((_QWORD *)v5[(unsigned int)v14] + 2) + 2LL * *((unsigned int *)v5[(unsigned int)v14] + 7);
        v17 = (unsigned int)(v14 + 1);
        if ( (unsigned int)v17 < (unsigned int)v8 && *((_DWORD *)v5[v17] + 1) == 13 )
        {
          do
          {
            v18 = v5[v17];
            if ( *((_DWORD *)v18 + 1) != 13 )
              break;
            v17 = (unsigned int)(v17 + 1);
            *(_DWORD *)(32LL * *(unsigned int *)(*((_QWORD *)this + 7) + 20LL) + *((_QWORD *)this + 7) + 48) += *((_DWORD *)v18 + 6);
          }
          while ( (unsigned int)v17 < (unsigned int)v8 );
          if ( !v11 )
          {
            v19 = 8 * v8;
            if ( !is_mul_ok(v8, 8u) )
              v19 = -1;
            v20 = __CFADD__(v19, 8);
            v21 = v19 + 8;
            if ( v20 )
              v21 = -1;
            v22 = CoTaskMemAlloc(v21);
            if ( !v22 )
            {
              a5 = 0;
LABEL_34:
              TSmartPointerArray<TSmartPointerArray<unsigned short>>::~TSmartPointerArray<TSmartPointerArray<unsigned short>>(&a5);
              return 2147942414LL;
            }
            v11 = (struct _XML_NODE_INFO **)(v22 + 1);
            *v22 = v8;
            `vector constructor iterator'(v22 + 1, 8u, v8, (void *(*)(void *))ATL::CComBSTR::CComBSTR);
            a5 = v11;
            if ( !v11 )
              goto LABEL_34;
          }
          v23 = (struct _XML_NODE_INFO *)CoTaskMemAlloc(
                                           saturated_mul(
                                             (unsigned int)(*(_DWORD *)(32LL
                                                                      * *(unsigned int *)(*((_QWORD *)this + 7) + 20LL)
                                                                      + *((_QWORD *)this + 7)
                                                                      + 48)
                                                          + 256),
                                             2u));
          v11[v16] = v23;
          if ( !v23 )
            goto LABEL_34;
          *(_QWORD *)(32LL * *(unsigned int *)(*((_QWORD *)this + 7) + 20LL) + *((_QWORD *)this + 7) + 56) = v23;
          v24 = v11[v16];
          memcpy_0(
            v24,
            (const void *)(*((_QWORD *)v5[v16] + 2) + 2LL * *((unsigned int *)v5[v16] + 7)),
            2LL * *((unsigned int *)v5[v16] + 6));
          v25 = (char *)v24 + 2 * *((unsigned int *)v5[v16] + 6);
          do
          {
            v26 = v12 + 1;
            v27 = v5[v26];
            v28 = v26;
            if ( *((_DWORD *)v27 + 1) != 13 )
              break;
            v12 = v26;
            memcpy_0(
              v25,
              (const void *)(*((_QWORD *)v27 + 2) + 2LL * *((unsigned int *)v27 + 7)),
              2LL * *((unsigned int *)v27 + 6));
            v25 += 2 * *((unsigned int *)v5[v28] + 6);
          }
          while ( v12 + 1 < (unsigned int)v8 );
        }
      }
      ++*(_DWORD *)(*((_QWORD *)this + 7) + 20LL);
    }
    ++v12;
  }
  v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 8) + 8LL))(
          *((_QWORD *)this + 8),
          *((_QWORD *)this + 7));
  TSmartPointerArray<TSmartPointerArray<unsigned short>>::~TSmartPointerArray<TSmartPointerArray<unsigned short>>(&a5);
  return v29;
}

```

## disassembly

```asm
0x180010fc0  push    rbx
0x180010fc2  push    rbp
0x180010fc3  push    rsi
0x180010fc4  push    rdi
0x180010fc5  push    r12
0x180010fc7  push    r13
0x180010fc9  push    r14
0x180010fcb  push    r15
0x180010fcd  sub     rsp, 28h
0x180010fd1  mov     r14, [rsp+68h+arg_20]
0x180010fd9  mov     rsi, rcx
0x180010fdc  mov     ecx, [rcx+30h]
0x180010fdf  movzx   r13d, r9w
0x180010fe3  xor     r9d, r9d
0x180010fe6  mov     rax, [r14]
0x180010fe9  cmp     [rax+0Ch], r9d
0x180010fed  jnz     short loc_180010FF5
0x180010fef  lea     eax, [rcx+1]
0x180010ff2  mov     [rsi+30h], eax
0x180010ff5  test    ecx, ecx
0x180010ff7  jz      loc_180011348
0x180010ffd  mov     rdx, [r14]
0x180011000  mov     r8d, [rdx+4]
0x180011004  mov     eax, r8d
0x180011007  sub     eax, 1
0x18001100a  jz      short loc_180011079
0x18001100c  sub     eax, 0Ch
0x18001100f  jz      short loc_18001101F
0x180011011  sub     eax, 3
0x180011014  jz      short loc_18001101F
0x180011016  cmp     eax, 2
0x180011019  jnz     loc_180011348
0x18001101f  mov     rax, [rsi+38h]
0x180011023  mov     [rax+18h], r8d
0x180011027  mov     rax, [rsi+38h]
0x18001102b  mov     [rax], ecx
0x18001102d  mov     rax, [r14]
0x180011030  mov     rcx, [rsi+38h]
0x180011034  mov     eax, [rax+18h]
0x180011037  mov     [rcx+4], eax
0x18001103a  mov     rax, [r14]
0x18001103d  mov     ecx, [rax+1Ch]
0x180011040  mov     rax, [rax+10h]
0x180011044  lea     rdx, [rax+rcx*2]
0x180011048  mov     rax, [rsi+38h]
0x18001104c  mov     [rax+8], rdx
0x180011050  mov     rax, [rsi+38h]
0x180011054  mov     [rax+14h], r9d
0x180011058  mov     rax, [rsi+38h]
0x18001105c  mov     [rax+10h], r9d
0x180011060  mov     rcx, [rsi+40h]
0x180011064  mov     rdx, [rsi+38h]
0x180011068  mov     rax, [rcx]
0x18001106b  mov     rax, [rax+8]
0x18001106f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011074  jmp     loc_18001134A
0x180011079  cmp     [rdx+10h], r9
0x18001107d  jz      loc_180011348
0x180011083  mov     rax, [rsi+38h]
0x180011087  mov     rbx, r9
0x18001108a  mov     [rsp+68h+arg_20], rbx
0x180011092  mov     ebp, 1
0x180011097  or      r10, 0FFFFFFFFFFFFFFFFh
0x18001109b  mov     dword ptr [rax+18h], 1
0x1800110a2  mov     rax, [rsi+38h]
0x1800110a6  mov     [rax], ecx
0x1800110a8  mov     rax, [r14]
0x1800110ab  mov     rcx, [rsi+38h]
0x1800110af  mov     eax, [rax+18h]
0x1800110b2  mov     [rcx+4], eax
0x1800110b5  mov     rax, [r14]
0x1800110b8  mov     ecx, [rax+1Ch]
0x1800110bb  mov     rax, [rax+10h]
0x1800110bf  lea     rdx, [rax+rcx*2]
0x1800110c3  mov     rax, [rsi+38h]
0x1800110c7  mov     [rax+8], rdx
0x1800110cb  mov     rax, [rsi+38h]
0x1800110cf  mov     [rax+14h], r9d
0x1800110d3  mov     rax, [rsi+38h]
0x1800110d7  mov     dword ptr [rax+10h], 1
0x1800110de  cmp     ebp, r13d
0x1800110e1  jnb     loc_180011321
0x1800110e7  mov     r8d, ebp
0x1800110ea  mov     rax, [r14+r8*8]
0x1800110ee  cmp     dword ptr [rax+4], 2
0x1800110f2  jnz     loc_1800112D8
0x1800110f8  mov     eax, [rax+18h]
0x1800110fb  mov     rdx, [rsi+38h]
0x1800110ff  mov     ecx, [rdx+14h]
0x180011102  inc     rcx
0x180011105  shl     rcx, 5
0x180011109  mov     [rcx+rdx], eax
0x18001110c  mov     rax, [r14+r8*8]
0x180011110  mov     r8, [rsi+38h]
0x180011114  mov     ecx, [rax+1Ch]
0x180011117  mov     rax, [rax+10h]
0x18001111b  lea     rdx, [rax+rcx*2]
0x18001111f  mov     eax, [r8+14h]
0x180011123  shl     rax, 5
0x180011127  lea     ecx, [rbp+1]
0x18001112a  mov     [rax+r8+28h], rdx
0x18001112f  cmp     ecx, r13d
0x180011132  jz      loc_1800112DF
0x180011138  mov     rax, [r14+rcx*8]
0x18001113c  mov     r15d, ecx
0x18001113f  cmp     dword ptr [rax+4], 0Dh
0x180011143  jnz     loc_1800112DF
0x180011149  mov     eax, [rax+18h]
0x18001114c  mov     ebp, ecx
0x18001114e  mov     rdx, [rsi+38h]
0x180011152  mov     ecx, [rdx+14h]
0x180011155  shl     rcx, 5
0x180011159  mov     [rcx+rdx+30h], eax
0x18001115d  mov     rax, [r14+r15*8]
0x180011161  mov     r8, [rsi+38h]
0x180011165  mov     ecx, [rax+1Ch]
0x180011168  mov     rax, [rax+10h]
0x18001116c  lea     rdx, [rax+rcx*2]
0x180011170  mov     eax, [r8+14h]
0x180011174  shl     rax, 5
0x180011178  mov     [rax+r8+38h], rdx
0x18001117d  lea     r8d, [rbp+1]
0x180011181  cmp     r8d, r13d
0x180011184  jnb     loc_1800112D1
0x18001118a  mov     rcx, [r14+r8*8]
0x18001118e  cmp     dword ptr [rcx+4], 0Dh
0x180011192  jnz     loc_1800112D1
0x180011198  mov     rax, [r14+r8*8]
0x18001119c  cmp     dword ptr [rax+4], 0Dh
0x1800111a0  jnz     short loc_1800111BC
0x1800111a2  mov     rdx, [rsi+38h]
0x1800111a6  inc     r8d
0x1800111a9  mov     eax, [rax+18h]
0x1800111ac  mov     ecx, [rdx+14h]
0x1800111af  shl     rcx, 5
0x1800111b3  add     [rcx+rdx+30h], eax
0x1800111b7  cmp     r8d, r13d
0x1800111ba  jb      short loc_180011198
0x1800111bc  test    rbx, rbx
0x1800111bf  jnz     short loc_180011218
0x1800111c1  lea     eax, [rbx+8]
0x1800111c4  mul     r13
0x1800111c7  cmovb   rax, r10
0x1800111cb  add     rax, 8
0x1800111cf  cmovb   rax, r10
0x1800111d3  mov     rcx, rax; cb
0x1800111d6  call    cs:__imp_CoTaskMemAlloc
0x1800111dc  test    rax, rax
0x1800111df  jz      loc_180011301
0x1800111e5  lea     rbx, [rax+8]
0x1800111e9  mov     [rax], r13
0x1800111ec  mov     rcx, rbx; void *
0x1800111ef  lea     r9, ??0CComBSTR@ATL@@QEAA@XZ; void *(*)(void *)
0x1800111f6  mov     r8, r13; unsigned __int64
0x1800111f9  mov     edx, 8; unsigned __int64
0x1800111fe  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180011203  mov     [rsp+68h+arg_20], rbx
0x18001120b  test    rbx, rbx
0x18001120e  jz      loc_18001130D
0x180011214  or      r10, 0FFFFFFFFFFFFFFFFh
0x180011218  mov     rcx, [rsi+38h]
0x18001121c  mov     eax, [rcx+14h]
0x18001121f  shl     rax, 5
0x180011223  mov     edx, [rax+rcx+30h]
0x180011227  mov     eax, 2
0x18001122c  add     edx, 100h
0x180011232  mul     rdx
0x180011235  cmovb   rax, r10
0x180011239  mov     rcx, rax; cb
0x18001123c  call    cs:__imp_CoTaskMemAlloc
0x180011242  mov     [rbx+r15*8], rax
0x180011246  test    rax, rax
0x180011249  jz      loc_18001130D
0x18001124f  mov     rdx, [rsi+38h]
0x180011253  mov     ecx, [rdx+14h]
0x180011256  shl     rcx, 5
0x18001125a  mov     [rcx+rdx+38h], rax
0x18001125f  mov     rax, [r14+r15*8]
0x180011263  mov     rdi, [rbx+r15*8]
0x180011267  mov     ecx, [rax+1Ch]
0x18001126a  mov     r8d, [rax+18h]
0x18001126e  mov     rax, [rax+10h]
0x180011272  add     r8, r8; Size
0x180011275  lea     rdx, [rax+rcx*2]; Src
0x180011279  mov     rcx, rdi; void *
0x18001127c  call    memcpy_0
0x180011281  mov     rax, [r14+r15*8]
0x180011285  mov     ecx, [rax+18h]
0x180011288  lea     r15, [rdi+rcx*2]
0x18001128c  lea     ecx, [rbp+1]
0x18001128f  mov     rax, [r14+rcx*8]
0x180011293  mov     edi, ecx
0x180011295  cmp     dword ptr [rax+4], 0Dh
0x180011299  jnz     short loc_1800112CA
0x18001129b  mov     r8d, [rax+18h]
0x18001129f  mov     ebp, ecx
0x1800112a1  mov     ecx, [rax+1Ch]
0x1800112a4  add     r8, r8; Size
0x1800112a7  mov     rax, [rax+10h]
0x1800112ab  lea     rdx, [rax+rcx*2]; Src
0x1800112af  mov     rcx, r15; void *
0x1800112b2  call    memcpy_0
0x1800112b7  mov     rax, [r14+rdi*8]
0x1800112bb  mov     ecx, [rax+18h]
0x1800112be  lea     eax, [rbp+1]
0x1800112c1  lea     r15, [r15+rcx*2]
0x1800112c5  cmp     eax, r13d
0x1800112c8  jb      short loc_18001128C
0x1800112ca  xor     r9d, r9d
0x1800112cd  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800112d1  mov     rax, [rsi+38h]
0x1800112d5  inc     dword ptr [rax+14h]
0x1800112d8  inc     ebp
0x1800112da  jmp     loc_1800110DE
0x1800112df  mov     rcx, [rsi+38h]
0x1800112e3  mov     eax, [rcx+14h]
0x1800112e6  shl     rax, 5
0x1800112ea  mov     [rax+rcx+30h], r9d
0x1800112ef  mov     rcx, [rsi+38h]
0x1800112f3  mov     eax, [rcx+14h]
0x1800112f6  shl     rax, 5
0x1800112fa  mov     [rax+rcx+38h], r9
0x1800112ff  jmp     short loc_1800112D1
0x180011301  mov     [rsp+68h+arg_20], 0
0x18001130d  lea     rcx, [rsp+68h+arg_20]
0x180011315  call    ??1?$TSmartPointerArray@V?$TSmartPointerArray@G@@@@QEAA@XZ; TSmartPointerArray<TSmartPointerArray<ushort>>::~TSmartPointerArray<TSmartPointerArray<ushort>>(void)
0x18001131a  mov     eax, 8007000Eh
0x18001131f  jmp     short loc_18001134A
0x180011321  mov     rcx, [rsi+40h]
0x180011325  mov     rdx, [rsi+38h]
0x180011329  mov     rax, [rcx]
0x18001132c  mov     rax, [rax+8]
0x180011330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011335  lea     rcx, [rsp+68h+arg_20]
0x18001133d  mov     ebx, eax
0x18001133f  call    ??1?$TSmartPointerArray@V?$TSmartPointerArray@G@@@@QEAA@XZ; TSmartPointerArray<TSmartPointerArray<ushort>>::~TSmartPointerArray<TSmartPointerArray<ushort>>(void)
0x180011344  mov     eax, ebx
0x180011346  jmp     short loc_18001134A
0x180011348  xor     eax, eax
0x18001134a  add     rsp, 28h
0x18001134e  pop     r15
0x180011350  pop     r14
0x180011352  pop     r13
0x180011354  pop     r12
0x180011356  pop     rdi
0x180011357  pop     rsi
0x180011358  pop     rbp
0x180011359  pop     rbx
0x18001135a  retn
```
