# CCMProviderInfoManager::AddSupportedPropInfos(ulong *,tagDBPROPINFOSET * *,ushort * *)

- ea: `0x180062c20`
- end: `0x180063029`
- name: `?AddSupportedPropInfos@CCMProviderInfoManager@@CAJPEAKPEAPEAUtagDBPROPINFOSET@@PEAPEAG@Z`
- size: `1033`
- prototype: `__int64 __fastcall(unsigned int *, struct tagDBPROPINFOSET **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001d6d8`

## callees

- `0x180013870`
- `0x180029560`
- `0x180062c20`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180062f57`
- `OLEAUT32!__imp_VariantInit` at `0x180062fa2`
- `OLEAUT32!__imp_VariantInit` at `0x180062f57`
- `OLEAUT32!__imp_VariantInit` at `0x180062fa2`
- `ole32!CoTaskMemAlloc` at `0x180062dc7`
- `ole32!CoTaskMemAlloc` at `0x180062dc7`
- `ole32!CoTaskMemRealloc` at `0x180062d3b`
- `ole32!CoTaskMemRealloc` at `0x180062ed7`
- `ole32!CoTaskMemRealloc` at `0x180062d3b`
- `ole32!CoTaskMemRealloc` at `0x180062ed7`

## string_xrefs

- `0x180062d82`: `OLE DB Services`
- `0x180062e14`: `OLE DB Services`

## pseudocode

```c
__int64 __fastcall CCMProviderInfoManager::AddSupportedPropInfos(
        unsigned int *a1,
        struct tagDBPROPINFOSET **a2,
        unsigned __int16 **a3)
{
  LPVOID *v3; // r14
  struct tagDBPROPINFOSET **v4; // r15
  unsigned __int64 v6; // r11
  unsigned __int64 v7; // r9
  unsigned int v8; // r10d
  unsigned int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v16; // rax
  __int64 v17; // rdi
  char *v18; // rax
  _OWORD *v19; // rax
  unsigned int i; // ecx
  struct tagDBPROPINFOSET *v21; // rbp
  __int64 v22; // rsi
  __int64 v23; // rax
  ULONG cPropertyInfos; // edx
  char v25; // r13
  PDBPROPINFO rgPropertyInfos; // rax
  int v27; // r15d
  ULONG v28; // ecx
  DBPROPINFO *v29; // rax
  DBPROPINFO *v30; // rdi
  __int64 v31; // rbx
  PDBPROPINFO v32; // rbx
  __int64 v33; // rdi
  unsigned __int64 v34; // r9
  unsigned int j; // r8d
  unsigned int v36; // r10d
  __int64 v37; // rdx
  __int64 v38; // rax
  char v41; // [rsp+70h] [rbp+18h]
  unsigned int v42; // [rsp+78h] [rbp+20h]

  v3 = (LPVOID *)a3;
  v42 = 0;
  v4 = a2;
  if ( a3 )
  {
    if ( *a3 )
    {
      v6 = (unsigned __int64)*a3 >> 1;
      v7 = 0;
      v8 = 0;
      if ( *a1 )
      {
        do
        {
          v9 = 0;
          v10 = (__int64)&(*v4)[v8];
          if ( *(_DWORD *)(v10 + 8) )
          {
            do
            {
              v11 = 6LL * v9;
              v12 = *(_QWORD *)(*(_QWORD *)v10 + 48LL * v9);
              if ( v12 > v7 )
                v7 = *(_QWORD *)(*(_QWORD *)v10 + 48LL * v9);
              ++v9;
              *(_QWORD *)(*(_QWORD *)v10 + 8 * v11) = v12 - 2 * v6;
            }
            while ( v9 < *(_DWORD *)(v10 + 8) );
          }
          ++v8;
        }
        while ( v8 < *a1 );
        v3 = (LPVOID *)a3;
      }
      if ( v7 < (unsigned __int64)*v3 )
      {
        v13 = -2147467259;
        if ( (bidGblFlags & 2) == 0 )
          return v13;
        OLEDBTraceErr(-2147467259, L"<CCMProviderInfoManager::AddSupportedPropInfos|OLEDB|ERR> ", 0x185u);
        if ( (bidGblFlags & 2) == 0 )
          return v13;
        v14 = 399369;
        return (unsigned int)bidTraceHR(
                               off_1800C8438[0],
                               v14,
                               L"<CCMProviderInfoManager::AddSupportedPropInfos|Trace|HR> ",
                               v13);
      }
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)(v7 + 2 * v16) );
      v17 = (unsigned int)(v7 + 2 * v16 + 2 - *(_DWORD *)v3);
      v42 = v7 + 2 * v16 + 2 - *(_DWORD *)v3;
      v18 = (char *)CoTaskMemRealloc(*v3, v17 + 76);
      if ( !v18 )
      {
        v13 = -2147024882;
        if ( (bidGblFlags & 2) == 0 )
          return v13;
        OLEDBTraceErr(-2147024882, L"<CCMProviderInfoManager::AddSupportedPropInfos|OLEDB|ERR> ", 0x18Du);
        if ( (bidGblFlags & 2) == 0 )
          return v13;
        v14 = 406537;
        return (unsigned int)bidTraceHR(
                               off_1800C8438[0],
                               v14,
                               L"<CCMProviderInfoManager::AddSupportedPropInfos|Trace|HR> ",
                               v13);
      }
      *v3 = v18;
      *(_OWORD *)&v18[v17] = *(_OWORD *)L"OLE DB Services";
      *(_OWORD *)&v18[v17 + 16] = *(_OWORD *)L"ervices";
      *(_OWORD *)&v18[v17 + 32] = xmmword_1800A00E0;
      *(_OWORD *)&v18[v17 + 48] = xmmword_1800A00F0;
      *(_OWORD *)&v18[v17 + 60] = *(__int128 *)((char *)&xmmword_1800A00F0 + 12);
    }
    else
    {
      v19 = CoTaskMemAlloc(0x4Cu);
      *v3 = v19;
      if ( !v19 )
      {
        v13 = -2147024882;
        if ( (bidGblFlags & 2) == 0 )
          return v13;
        OLEDBTraceErr(-2147024882, L"<CCMProviderInfoManager::AddSupportedPropInfos|OLEDB|ERR> ", 0x199u);
        if ( (bidGblFlags & 2) == 0 )
          return v13;
        v14 = 418825;
        return (unsigned int)bidTraceHR(
                               off_1800C8438[0],
                               v14,
                               L"<CCMProviderInfoManager::AddSupportedPropInfos|Trace|HR> ",
                               v13);
      }
      *v19 = *(_OWORD *)L"OLE DB Services";
      v19[1] = *(_OWORD *)L"ervices";
      v19[2] = xmmword_1800A00E0;
      v19[3] = xmmword_1800A00F0;
      *(_OWORD *)((char *)v19 + 60) = *(__int128 *)((char *)&xmmword_1800A00F0 + 12);
    }
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *a1 )
      goto LABEL_50;
    v21 = *v4;
    v22 = i;
    v23 = *(_QWORD *)&DBPROPSET_DBINIT.Data1 - *(_QWORD *)&(*v4)[v22].guidPropertySet.Data1;
    if ( *(_QWORD *)&DBPROPSET_DBINIT.Data1 == *(_QWORD *)&(*v4)[v22].guidPropertySet.Data1 )
      v23 = *(_QWORD *)DBPROPSET_DBINIT.Data4 - *(_QWORD *)v21[v22].guidPropertySet.Data4;
    if ( !v23 )
      break;
  }
  cPropertyInfos = v21[v22].cPropertyInfos;
  v25 = 1;
  rgPropertyInfos = v21[v22].rgPropertyInfos;
  v27 = 2;
  v41 = 1;
  v28 = 0;
  if ( cPropertyInfos )
  {
    while ( rgPropertyInfos->dwPropertyID != 248 )
    {
      if ( rgPropertyInfos->dwPropertyID == 11 )
      {
        v41 = 0;
        goto LABEL_39;
      }
LABEL_40:
      ++v28;
      ++rgPropertyInfos;
      if ( v28 >= cPropertyInfos )
        goto LABEL_41;
    }
    v25 = 0;
LABEL_39:
    --v27;
    goto LABEL_40;
  }
LABEL_41:
  v29 = (DBPROPINFO *)CoTaskMemRealloc(v21[v22].rgPropertyInfos, 48LL * (cPropertyInfos + v27));
  v30 = v29;
  if ( !v29 )
  {
    v13 = -2147024882;
    if ( (bidGblFlags & 2) == 0 )
      return v13;
    OLEDBTraceErr(-2147024882, L"<CCMProviderInfoManager::AddSupportedPropInfos|OLEDB|ERR> ", 0x1C6u);
    if ( (bidGblFlags & 2) == 0 )
      return v13;
    v14 = 464905;
    return (unsigned int)bidTraceHR(
                           off_1800C8438[0],
                           v14,
                           L"<CCMProviderInfoManager::AddSupportedPropInfos|Trace|HR> ",
                           v13);
  }
  v21[v22].rgPropertyInfos = v29;
  if ( v25 )
  {
    v31 = v21[v22].cPropertyInfos;
    v29[v31].dwPropertyID = 248;
    v29[v31].dwFlags = 1552;
    v29[v31].vtType = 3;
    VariantInit(&v29[v31].vValues);
    v30[v31].pwszDescription = (LPOLESTR)v42;
  }
  if ( v41 )
  {
    v32 = v21[v22].rgPropertyInfos;
    v33 = v21[v22].cPropertyInfos + (v25 != 0);
    v32[v33].dwPropertyID = 11;
    v32[v33].dwFlags = 1552;
    v32[v33].vtType = 11;
    VariantInit(&v32[v33].vValues);
    v32[v33].pwszDescription = (LPOLESTR)(v42 + 32);
  }
  v21[v22].cPropertyInfos += v27;
  v4 = a2;
LABEL_50:
  if ( v3 )
  {
    if ( *v3 )
    {
      v34 = (unsigned __int64)*v3 >> 1;
      for ( j = 0; j < *a1; ++j )
      {
        v36 = 0;
        v37 = (__int64)&(*v4)[j];
        if ( *(_DWORD *)(v37 + 8) )
        {
          do
          {
            v38 = v36++;
            *(_QWORD *)(48 * v38 + *(_QWORD *)v37) += 2 * v34;
          }
          while ( v36 < *(_DWORD *)(v37 + 8) );
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180062c20  mov     [rsp+arg_0], rbx
0x180062c25  mov     [rsp+arg_10], r8
0x180062c2a  mov     [rsp+arg_8], rdx
0x180062c2f  push    rbp
0x180062c30  push    rsi
0x180062c31  push    rdi
0x180062c32  push    r12
0x180062c34  push    r13
0x180062c36  push    r14
0x180062c38  push    r15
0x180062c3a  sub     rsp, 20h
0x180062c3e  xor     ebx, ebx
0x180062c40  mov     r14, r8
0x180062c43  mov     [rsp+58h+arg_18], ebx
0x180062c47  mov     r15, rdx
0x180062c4a  mov     r12, rcx
0x180062c4d  test    r8, r8
0x180062c50  jz      loc_180062E4A
0x180062c56  mov     r11, [r8]
0x180062c59  test    r11, r11
0x180062c5c  jz      loc_180062DC2
0x180062c62  shr     r11, 1
0x180062c65  mov     r9d, ebx
0x180062c68  mov     r10d, ebx
0x180062c6b  cmp     [rcx], ebx
0x180062c6d  jbe     short loc_180062CBF
0x180062c6f  xor     r14d, r14d
0x180062c72  mov     r8d, r10d
0x180062c75  mov     ebx, r14d
0x180062c78  shl     r8, 5
0x180062c7c  add     r8, [r15]
0x180062c7f  cmp     [r8+8], r14d
0x180062c83  jbe     short loc_180062CAF
0x180062c85  lea     rdi, [r11+r11]
0x180062c89  mov     rcx, [r8]
0x180062c8c  mov     eax, ebx
0x180062c8e  lea     rdx, [rax+rax*2]
0x180062c92  add     rdx, rdx
0x180062c95  mov     rax, [rcx+rdx*8]
0x180062c99  cmp     rax, r9
0x180062c9c  cmova   r9, rax
0x180062ca0  sub     rax, rdi
0x180062ca3  inc     ebx
0x180062ca5  mov     [rcx+rdx*8], rax
0x180062ca9  cmp     ebx, [r8+8]
0x180062cad  jb      short loc_180062C89
0x180062caf  inc     r10d
0x180062cb2  cmp     r10d, [r12]
0x180062cb6  jb      short loc_180062C72
0x180062cb8  mov     r14, [rsp+58h+arg_10]
0x180062cbd  xor     ebx, ebx
0x180062cbf  cmp     r9, [r14]
0x180062cc2  jnb     short loc_180062D15
0x180062cc4  mov     eax, cs:_bidGblFlags
0x180062cca  mov     ebx, 80004005h
0x180062ccf  test    al, 2
0x180062cd1  jz      short loc_180062D0E
0x180062cd3  mov     r8d, 185h; unsigned int
0x180062cd9  lea     rdx, aCcmproviderinf_23; "<CCMProviderInfoManager::AddSupportedPr"...
0x180062ce0  mov     ecx, ebx; int
0x180062ce2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180062ce7  mov     eax, cs:_bidGblFlags
0x180062ced  test    al, 2
0x180062cef  jz      short loc_180062D0E
0x180062cf1  mov     edx, 61809h
0x180062cf6  mov     rcx, cs:off_1800C8438; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180062cfd  lea     r8, aCcmproviderinf_3; "<CCMProviderInfoManager::AddSupportedPr"...
0x180062d04  mov     r9d, ebx
0x180062d07  call    _bidTraceHR
0x180062d0c  mov     ebx, eax
0x180062d0e  mov     eax, ebx
0x180062d10  jmp     loc_180063014
0x180062d15  or      rax, 0FFFFFFFFFFFFFFFFh
0x180062d19  inc     rax
0x180062d1c  cmp     [r9+rax*2], bx
0x180062d21  jnz     short loc_180062D19
0x180062d23  mov     rcx, [r14]; pv
0x180062d26  lea     edi, ds:2[rax*2]
0x180062d2d  sub     edi, [r14]
0x180062d30  add     edi, r9d
0x180062d33  mov     [rsp+58h+arg_18], edi
0x180062d37  lea     rdx, [rdi+4Ch]; cb
0x180062d3b  call    cs:__imp_CoTaskMemRealloc
0x180062d41  test    rax, rax
0x180062d44  jnz     short loc_180062D7D
0x180062d46  mov     eax, cs:_bidGblFlags
0x180062d4c  mov     ebx, 8007000Eh
0x180062d51  test    al, 2
0x180062d53  jz      short loc_180062D0E
0x180062d55  mov     r8d, 18Dh; unsigned int
0x180062d5b  lea     rdx, aCcmproviderinf_23; "<CCMProviderInfoManager::AddSupportedPr"...
0x180062d62  mov     ecx, ebx; int
0x180062d64  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180062d69  mov     eax, cs:_bidGblFlags
0x180062d6f  test    al, 2
0x180062d71  jz      short loc_180062D0E
0x180062d73  mov     edx, 63409h
0x180062d78  jmp     loc_180062CF6
0x180062d7d  mov     [r14], rax
0x180062d80  xor     ebx, ebx
0x180062d82  movaps  xmm0, xmmword ptr cs:aOleDbServices_0; "OLE DB Services"
0x180062d89  movups  xmmword ptr [rdi+rax], xmm0
0x180062d8d  movaps  xmm1, xmmword ptr cs:aOleDbServices_0+10h; "ervices"
0x180062d94  movups  xmmword ptr [rdi+rax+10h], xmm1
0x180062d99  movaps  xmm0, cs:xmmword_1800A00E0
0x180062da0  movups  xmmword ptr [rdi+rax+20h], xmm0
0x180062da5  movaps  xmm1, cs:xmmword_1800A00F0
0x180062dac  movups  xmmword ptr [rdi+rax+30h], xmm1
0x180062db1  movups  xmm0, cs:xmmword_1800A00F0+0Ch
0x180062db8  movups  xmmword ptr [rdi+rax+3Ch], xmm0
0x180062dbd  jmp     loc_180062E4A
0x180062dc2  mov     ecx, 4Ch ; 'L'; cb
0x180062dc7  call    cs:__imp_CoTaskMemAlloc
0x180062dcd  mov     [r14], rax
0x180062dd0  test    rax, rax
0x180062dd3  jnz     short loc_180062E14
0x180062dd5  mov     eax, cs:_bidGblFlags
0x180062ddb  mov     ebx, 8007000Eh
0x180062de0  test    al, 2
0x180062de2  jz      loc_180062D0E
0x180062de8  mov     r8d, 199h; unsigned int
0x180062dee  lea     rdx, aCcmproviderinf_23; "<CCMProviderInfoManager::AddSupportedPr"...
0x180062df5  mov     ecx, ebx; int
0x180062df7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180062dfc  mov     eax, cs:_bidGblFlags
0x180062e02  test    al, 2
0x180062e04  jz      loc_180062D0E
0x180062e0a  mov     edx, 66409h
0x180062e0f  jmp     loc_180062CF6
0x180062e14  movaps  xmm0, xmmword ptr cs:aOleDbServices_0; "OLE DB Services"
0x180062e1b  movups  xmmword ptr [rax], xmm0
0x180062e1e  movaps  xmm1, xmmword ptr cs:aOleDbServices_0+10h; "ervices"
0x180062e25  movups  xmmword ptr [rax+10h], xmm1
0x180062e29  movaps  xmm0, cs:xmmword_1800A00E0
0x180062e30  movups  xmmword ptr [rax+20h], xmm0
0x180062e34  movaps  xmm1, cs:xmmword_1800A00F0
0x180062e3b  movups  xmmword ptr [rax+30h], xmm1
0x180062e3f  movups  xmm0, cs:xmmword_1800A00F0+0Ch
0x180062e46  movups  xmmword ptr [rax+3Ch], xmm0
0x180062e4a  mov     ecx, ebx
0x180062e4c  cmp     ecx, [r12]
0x180062e50  jnb     loc_180062FBF
0x180062e56  mov     rbp, [r15]
0x180062e59  mov     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x180062e60  mov     esi, ecx
0x180062e62  shl     rsi, 5
0x180062e66  sub     rax, [rsi+rbp+0Ch]
0x180062e6b  jnz     short loc_180062E79
0x180062e6d  mov     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x180062e74  sub     rax, [rsi+rbp+14h]
0x180062e79  test    rax, rax
0x180062e7c  jz      short loc_180062E82
0x180062e7e  inc     ecx
0x180062e80  jmp     short loc_180062E4C
0x180062e82  mov     edx, [rsi+rbp+8]
0x180062e86  mov     r13b, 1
0x180062e89  mov     rax, [rsi+rbp]
0x180062e8d  mov     r15d, 2
0x180062e93  mov     byte ptr [rsp+58h+arg_10], r13b
0x180062e98  mov     ecx, ebx
0x180062e9a  test    edx, edx
0x180062e9c  jz      short loc_180062EC7
0x180062e9e  or      r8d, 0FFFFFFFFh
0x180062ea2  cmp     dword ptr [rax+8], 0F8h
0x180062ea9  jnz     short loc_180062EB0
0x180062eab  mov     r13b, bl
0x180062eae  jmp     short loc_180062EBA
0x180062eb0  cmp     dword ptr [rax+8], 0Bh
0x180062eb4  jnz     short loc_180062EBD
0x180062eb6  mov     byte ptr [rsp+58h+arg_10], bl
0x180062eba  add     r15d, r8d
0x180062ebd  inc     ecx
0x180062ebf  add     rax, 30h ; '0'
0x180062ec3  cmp     ecx, edx
0x180062ec5  jb      short loc_180062EA2
0x180062ec7  mov     rcx, [rsi+rbp]; pv
0x180062ecb  lea     eax, [rdx+r15]
0x180062ecf  lea     rdx, [rax+rax*2]
0x180062ed3  shl     rdx, 4; cb
0x180062ed7  call    cs:__imp_CoTaskMemRealloc
0x180062edd  mov     rdi, rax
0x180062ee0  test    rax, rax
0x180062ee3  jnz     short loc_180062F24
0x180062ee5  mov     eax, cs:_bidGblFlags
0x180062eeb  mov     ebx, 8007000Eh
0x180062ef0  test    al, 2
0x180062ef2  jz      loc_180062D0E
0x180062ef8  mov     r8d, 1C6h; unsigned int
0x180062efe  lea     rdx, aCcmproviderinf_23; "<CCMProviderInfoManager::AddSupportedPr"...
0x180062f05  mov     ecx, ebx; int
0x180062f07  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180062f0c  mov     eax, cs:_bidGblFlags
0x180062f12  test    al, 2
0x180062f14  jz      loc_180062D0E
0x180062f1a  mov     edx, 71809h
0x180062f1f  jmp     loc_180062CF6
0x180062f24  mov     [rsi+rbp], rdi
0x180062f28  test    r13b, r13b
0x180062f2b  jz      short loc_180062F67
0x180062f2d  mov     eax, [rsi+rbp+8]
0x180062f31  lea     rbx, [rax+rax*2]
0x180062f35  shl     rbx, 4
0x180062f39  lea     rcx, [rbx+18h]
0x180062f3d  mov     dword ptr [rbx+rdi+8], 0F8h
0x180062f45  add     rcx, rdi; pvarg
0x180062f48  mov     dword ptr [rbx+rdi+0Ch], 610h
0x180062f50  mov     word ptr [rbx+rdi+10h], 3
0x180062f57  call    cs:__imp_VariantInit
0x180062f5d  mov     eax, [rsp+58h+arg_18]
0x180062f61  mov     [rbx+rdi], rax
0x180062f65  xor     ebx, ebx
0x180062f67  cmp     byte ptr [rsp+58h+arg_10], bl
0x180062f6b  jz      short loc_180062FB5
0x180062f6d  mov     eax, ebx
0x180062f6f  test    r13b, r13b
0x180062f72  mov     rbx, [rsi+rbp]
0x180062f76  setnz   al
0x180062f79  add     eax, [rsi+rbp+8]
0x180062f7d  lea     rcx, [rbx+18h]
0x180062f81  lea     rdi, [rax+rax*2]
0x180062f85  mov     eax, 0Bh
0x180062f8a  shl     rdi, 4
0x180062f8e  add     rcx, rdi; pvarg
0x180062f91  mov     [rdi+rbx+8], eax
0x180062f95  mov     dword ptr [rdi+rbx+0Ch], 610h
0x180062f9d  mov     [rdi+rbx+10h], ax
0x180062fa2  call    cs:__imp_VariantInit
0x180062fa8  mov     ecx, [rsp+58h+arg_18]
0x180062fac  add     ecx, 20h ; ' '
0x180062faf  mov     [rdi+rbx], rcx
0x180062fb3  xor     ebx, ebx
0x180062fb5  add     [rsi+rbp+8], r15d
0x180062fba  mov     r15, [rsp+58h+arg_8]
0x180062fbf  test    r14, r14
0x180062fc2  jz      short loc_180063012
0x180062fc4  mov     r9, [r14]
0x180062fc7  test    r9, r9
0x180062fca  jz      short loc_180063012
0x180062fcc  shr     r9, 1
0x180062fcf  mov     r8d, ebx
0x180062fd2  cmp     [r12], ebx
0x180062fd6  jbe     short loc_180063012
0x180062fd8  mov     edx, r8d
0x180062fdb  mov     r10d, ebx
0x180062fde  shl     rdx, 5
0x180062fe2  add     rdx, [r15]
0x180062fe5  cmp     [rdx+8], ebx
0x180062fe8  jbe     short loc_180063009
0x180062fea  lea     r11, [r9+r9]
0x180062fee  mov     eax, r10d
0x180062ff1  inc     r10d
0x180062ff4  lea     rcx, [rax+rax*2]
0x180062ff8  mov     rax, [rdx]
0x180062ffb  shl     rcx, 4
0x180062fff  add     [rcx+rax], r11
0x180063003  cmp     r10d, [rdx+8]
0x180063007  jb      short loc_180062FEE
0x180063009  inc     r8d
0x18006300c  cmp     r8d, [r12]
0x180063010  jb      short loc_180062FD8
0x180063012  xor     eax, eax
0x180063014  mov     rbx, [rsp+58h+arg_0]
0x180063019  add     rsp, 20h
0x18006301d  pop     r15
0x18006301f  pop     r14
0x180063021  pop     r13
0x180063023  pop     r12
0x180063025  pop     rdi
0x180063026  pop     rsi
0x180063027  pop     rbp
0x180063028  retn
```
