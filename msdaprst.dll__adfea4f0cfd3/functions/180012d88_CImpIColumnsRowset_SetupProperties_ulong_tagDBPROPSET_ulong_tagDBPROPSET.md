# CImpIColumnsRowset::SetupProperties(ulong *,tagDBPROPSET * *,ulong,tagDBPROPSET *)

- ea: `0x180012d88`
- end: `0x18001316d`
- name: `?SetupProperties@CImpIColumnsRowset@@AEAAXPEAKPEAPEAUtagDBPROPSET@@KPEAU2@@Z`
- size: `997`
- prototype: `void __fastcall(CImpIColumnsRowset *__hidden this, unsigned int *, struct tagDBPROPSET **, unsigned int, struct tagDBPROPSET *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180012300`

## callees

- `0x180012d88`
- `0x18001b008`
- `0x18002dc20`
- `0x18002dca4`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180012e38`
- `ole32!CoTaskMemAlloc` at `0x180012ef1`
- `ole32!CoTaskMemAlloc` at `0x180013086`
- `ole32!CoTaskMemAlloc` at `0x180012e38`
- `ole32!CoTaskMemAlloc` at `0x180012ef1`
- `ole32!CoTaskMemAlloc` at `0x180013086`
- `OLEAUT32!__imp_VariantInit` at `0x180012f5c`
- `OLEAUT32!__imp_VariantInit` at `0x18001312f`
- `OLEAUT32!__imp_VariantInit` at `0x180012f5c`
- `OLEAUT32!__imp_VariantInit` at `0x18001312f`
- `OLEAUT32!__imp_VariantCopy` at `0x180012f9e`
- `OLEAUT32!__imp_VariantCopy` at `0x180012f9e`

## pseudocode

```c
void __fastcall CImpIColumnsRowset::SetupProperties(
        CImpIColumnsRowset *this,
        unsigned int *a2,
        struct tagDBPROPSET **a3,
        unsigned int a4,
        struct tagDBPROPSET *a5)
{
  int v5; // r14d
  unsigned int i; // r8d
  int v10; // r8d
  __int64 v11; // r9
  __int64 j; // rdx
  struct tagDBPROPSET *v13; // rax
  unsigned int k; // r12d
  __int64 v15; // rbx
  struct tagDBPROPSET *v16; // rcx
  __int64 v17; // rax
  ULONG cProperties; // eax
  __int64 m; // rbp
  __int64 v20; // r8
  __int64 n; // rbp
  HRESULT v22; // r14d
  unsigned int v23; // ebp
  __int64 v24; // rbx
  __int64 v25; // rdi
  __int64 v26; // rbx
  int v27; // [rsp+70h] [rbp+8h]
  int v28; // [rsp+88h] [rbp+20h]

  v5 = 0;
  v28 = 0;
  v27 = -1;
  for ( i = 0; ; i = v10 + 1 )
  {
    if ( i >= a4 )
      goto LABEL_11;
    if ( (unsigned int)IsSame(&a5[i].guidPropertySet, &DBPROPSET_ROWSET) )
      break;
  }
  v27 = v10;
  if ( v10 == -1 )
  {
LABEL_11:
    *a2 = a4 + 1;
    goto LABEL_12;
  }
  *a2 = a4;
  for ( j = 0; (unsigned int)j < *(ULONG *)((char *)&a5->cProperties + v11); j = (unsigned int)(j + 1) )
  {
    if ( (*(DBPROP **)((char *)&a5->rgProperties + v11))[j].dwPropertyID == 134 )
    {
      v5 = 1;
      v28 = 1;
      break;
    }
  }
LABEL_12:
  v13 = (struct tagDBPROPSET *)CoTaskMemAlloc(32LL * *a2);
  *a3 = v13;
  if ( !v13 )
  {
    *a2 = 0;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180049930[0] )
        bidTraceW(off_1800491D0[0], 324608, off_180049930[0], 2147942414LL, 317);
    }
    goto LABEL_44;
  }
  for ( k = 0; k < a4; ++k )
  {
    v15 = k;
    (*a3)[v15].guidPropertySet = a5[v15].guidPropertySet;
    v16 = &(*a3)[v15];
    v17 = *(_QWORD *)&v16->guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_ROWSET.Data1;
    if ( !v17 )
      v17 = *(_QWORD *)v16->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_ROWSET.Data4;
    if ( v17 || v5 )
      cProperties = a5[v15].cProperties;
    else
      cProperties = a5[v15].cProperties + 1;
    v16->cProperties = cProperties;
    (*a3)[v15].rgProperties = (DBPROP *)CoTaskMemAlloc(72LL * (*a3)[v15].cProperties);
    if ( !(*a3)[k].rgProperties )
    {
      (*a3)[v15].cProperties = 0;
      if ( (bidGblFlags & 2) != 0 && off_180049928[0] )
        bidTraceW(off_1800491D0[0], 339968, off_180049928[0], 2147942414LL, 332);
      goto LABEL_44;
    }
    for ( m = 0; (unsigned int)m < a5[v15].cProperties; m = (unsigned int)(m + 1) )
    {
      v20 = m;
      (*a3)[k].rgProperties[v20].dwPropertyID = a5[k].rgProperties[m].dwPropertyID;
      (*a3)[k].rgProperties[v20].dwOptions = a5[k].rgProperties[m].dwOptions;
      VariantInit(&(*a3)[v15].rgProperties[m].vValue);
    }
    for ( n = 0; (unsigned int)n < a5[v15].cProperties; n = (unsigned int)(n + 1) )
    {
      v22 = VariantCopy(&(*a3)[k].rgProperties[n].vValue, &a5[k].rgProperties[n].vValue);
      if ( v22 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049920[0] )
          bidTraceW(off_1800491D0[0], 354304, off_180049920[0], (unsigned int)v22, 346);
        ThrowHR(v22);
      }
    }
    v5 = v28;
  }
  v23 = v27;
  if ( v27 == -1 )
  {
    v23 = *a2 - 1;
    v24 = v23;
    (*a3)[v24].guidPropertySet = DBPROPSET_ROWSET;
    (*a3)[v24].cProperties = 1;
    (*a3)[v24].rgProperties = (DBPROP *)CoTaskMemAlloc(72LL * (*a3)[v24].cProperties);
    if ( !(*a3)[v24].rgProperties )
    {
      (*a3)[v24].cProperties = 0;
      if ( (bidGblFlags & 2) != 0 && off_180049918[0] )
        bidTraceW(off_1800491D0[0], 368640, off_180049918[0], 2147942414LL, 360);
LABEL_44:
      ThrowHR(-2147024882);
    }
  }
  if ( !v5 )
  {
    v25 = v23;
    v26 = (*a3)[v25].cProperties - 1;
    (*a3)[v25].rgProperties[v26].dwPropertyID = 134;
    (*a3)[v25].rgProperties[v26].dwOptions = 0;
    VariantInit(&(*a3)[v25].rgProperties[v26].vValue);
    (*a3)[v25].rgProperties[v26].vValue.vt = 11;
    (*a3)[v25].rgProperties[v26].vValue.iVal = -1;
  }
}

```

## disassembly

```asm
0x180012d88  mov     [rsp+arg_8], rbx
0x180012d8d  mov     [rsp+arg_0], rcx
0x180012d92  push    rbp
0x180012d93  push    rsi
0x180012d94  push    rdi
0x180012d95  push    r12
0x180012d97  push    r13
0x180012d99  push    r14
0x180012d9b  push    r15
0x180012d9d  sub     rsp, 30h
0x180012da1  mov     rdi, [rsp+68h+arg_20]
0x180012da9  xor     r14d, r14d
0x180012dac  or      ebx, 0FFFFFFFFh
0x180012daf  mov     [rsp+68h+arg_18], r14d
0x180012db7  mov     rsi, r8
0x180012dba  mov     dword ptr [rsp+68h+arg_0], ebx
0x180012dbe  xor     r8d, r8d
0x180012dc1  mov     r13d, r9d
0x180012dc4  mov     r15, rdx
0x180012dc7  cmp     r8d, r13d
0x180012dca  jnb     short loc_180012E2A
0x180012dcc  mov     r9d, r8d
0x180012dcf  lea     rcx, [rdi+0Ch]
0x180012dd3  shl     r9, 5
0x180012dd7  lea     rdx, DBPROPSET_ROWSET; struct _GUID *
0x180012dde  add     rcx, r9; struct _GUID *
0x180012de1  call    ?IsSame@@YAHAEBU_GUID@@0@Z; IsSame(_GUID const &,_GUID const &)
0x180012de6  test    eax, eax
0x180012de8  jnz     short loc_180012DEF
0x180012dea  inc     r8d
0x180012ded  jmp     short loc_180012DC7
0x180012def  mov     dword ptr [rsp+68h+arg_0], r8d
0x180012df4  cmp     r8d, ebx
0x180012df7  jz      short loc_180012E2A
0x180012df9  mov     [r15], r13d
0x180012dfc  xor     edx, edx
0x180012dfe  cmp     edx, [r9+rdi+8]
0x180012e03  jnb     short loc_180012E31
0x180012e05  mov     rax, [r9+rdi]
0x180012e09  lea     rcx, [rdx+rdx*8]
0x180012e0d  cmp     dword ptr [rax+rcx*8], 86h
0x180012e14  jz      short loc_180012E1A
0x180012e16  inc     edx
0x180012e18  jmp     short loc_180012DFE
0x180012e1a  mov     r14d, 1
0x180012e20  mov     [rsp+68h+arg_18], r14d
0x180012e28  jmp     short loc_180012E31
0x180012e2a  lea     eax, [r13+1]
0x180012e2e  mov     [r15], eax
0x180012e31  mov     ecx, [r15]
0x180012e34  shl     rcx, 5; cb
0x180012e38  call    cs:__imp_CoTaskMemAlloc
0x180012e3f  nop     dword ptr [rax+rax+00h]
0x180012e44  mov     [rsi], rax
0x180012e47  test    rax, rax
0x180012e4a  jnz     short loc_180012E85
0x180012e4c  mov     [r15], eax
0x180012e4f  test    byte ptr cs:_bidGblFlags, 2
0x180012e56  jz      loc_1800130E6
0x180012e5c  mov     rax, cs:off_180049930; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012e63  test    rax, rax
0x180012e66  jz      loc_1800130E6
0x180012e6c  mov     r8, cs:off_180049930; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012e73  mov     edx, 4F400h
0x180012e78  mov     [rsp+68h+var_48], 13Dh
0x180012e80  jmp     loc_1800130D4
0x180012e85  xor     r12d, r12d
0x180012e88  cmp     r12d, r13d
0x180012e8b  jnb     loc_180013044
0x180012e91  mov     rax, [rsi]
0x180012e94  mov     ebx, r12d
0x180012e97  shl     rbx, 5
0x180012e9b  movups  xmm0, xmmword ptr [rbx+rdi+0Ch]
0x180012ea0  movdqu  xmmword ptr [rax+rbx+0Ch], xmm0
0x180012ea6  mov     rcx, [rsi]
0x180012ea9  add     rcx, rbx
0x180012eac  mov     rax, [rcx+0Ch]
0x180012eb0  sub     rax, qword ptr cs:DBPROPSET_ROWSET.Data1
0x180012eb7  jnz     short loc_180012EC4
0x180012eb9  mov     rax, [rcx+14h]
0x180012ebd  sub     rax, qword ptr cs:DBPROPSET_ROWSET.Data4
0x180012ec4  test    rax, rax
0x180012ec7  jnz     short loc_180012ED6
0x180012ec9  test    r14d, r14d
0x180012ecc  jnz     short loc_180012ED6
0x180012ece  mov     eax, [rbx+rdi+8]
0x180012ed2  inc     eax
0x180012ed4  jmp     short loc_180012EDA
0x180012ed6  mov     eax, [rbx+rdi+8]
0x180012eda  mov     edx, 8
0x180012edf  mov     [rdx+rcx], eax
0x180012ee2  mov     rax, [rsi]
0x180012ee5  mov     ecx, [rax+rbx+8]
0x180012ee9  lea     rcx, [rcx+rcx*8]
0x180012eed  shl     rcx, 3; cb
0x180012ef1  call    cs:__imp_CoTaskMemAlloc
0x180012ef8  nop     dword ptr [rax+rax+00h]
0x180012efd  mov     rcx, [rsi]
0x180012f00  mov     [rbx+rcx], rax
0x180012f04  mov     rax, [rsi]
0x180012f07  cmp     qword ptr [rax+rbx], 0
0x180012f0c  jz      loc_180013006
0x180012f12  xor     ebp, ebp
0x180012f14  cmp     [rbx+rdi+8], ebp
0x180012f18  jbe     short loc_180012F70
0x180012f1a  mov     rax, [rsi]
0x180012f1d  lea     r8, ds:0[rbp*8]
0x180012f25  mov     rdx, [rbx+rdi]
0x180012f29  add     r8, rbp
0x180012f2c  mov     rcx, [rax+rbx]
0x180012f30  mov     eax, [rdx+r8*8]
0x180012f34  mov     [rcx+r8*8], eax
0x180012f38  mov     rax, [rsi]
0x180012f3b  mov     rdx, [rbx+rdi]
0x180012f3f  mov     rcx, [rax+rbx]
0x180012f43  mov     eax, [rdx+r8*8+4]
0x180012f48  mov     [rcx+r8*8+4], eax
0x180012f4d  mov     rax, [rsi]
0x180012f50  mov     rcx, [rbx+rax]
0x180012f54  lea     rcx, [rcx+r8*8]
0x180012f58  add     rcx, 30h ; '0'; pvarg
0x180012f5c  call    cs:__imp_VariantInit
0x180012f63  nop     dword ptr [rax+rax+00h]
0x180012f68  inc     ebp
0x180012f6a  cmp     ebp, [rbx+rdi+8]
0x180012f6e  jb      short loc_180012F1A
0x180012f70  xor     ebp, ebp
0x180012f72  cmp     ebp, [rbx+rdi+8]
0x180012f76  jnb     short loc_180012FB5
0x180012f78  mov     rax, [rsi]
0x180012f7b  lea     r8, ds:0[rbp*8]
0x180012f83  mov     rdx, [rbx+rdi]
0x180012f87  add     r8, rbp
0x180012f8a  add     rdx, 30h ; '0'
0x180012f8e  mov     rcx, [rax+rbx]
0x180012f92  lea     rdx, [rdx+r8*8]; pvargSrc
0x180012f96  lea     rcx, [rcx+r8*8]
0x180012f9a  add     rcx, 30h ; '0'; pvargDest
0x180012f9e  call    cs:__imp_VariantCopy
0x180012fa5  nop     dword ptr [rax+rax+00h]
0x180012faa  mov     r14d, eax
0x180012fad  test    eax, eax
0x180012faf  js      short loc_180012FC5
0x180012fb1  inc     ebp
0x180012fb3  jmp     short loc_180012F72
0x180012fb5  mov     r14d, [rsp+68h+arg_18]
0x180012fbd  inc     r12d
0x180012fc0  jmp     loc_180012E88
0x180012fc5  test    byte ptr cs:_bidGblFlags, 2
0x180012fcc  jz      short loc_180012FFD
0x180012fce  mov     rax, cs:off_180049920; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012fd5  test    rax, rax
0x180012fd8  jz      short loc_180012FFD
0x180012fda  mov     r8, cs:off_180049920; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012fe1  mov     r9d, r14d
0x180012fe4  mov     rcx, cs:off_1800491D0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180012feb  mov     edx, 56800h
0x180012ff0  mov     [rsp+68h+var_48], 15Ah
0x180012ff8  call    _bidTraceW
0x180012ffd  mov     ecx, r14d; int
0x180013000  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180013006  mov     dword ptr [rax+rbx+8], 0
0x18001300e  test    byte ptr cs:_bidGblFlags, 2
0x180013015  jz      loc_1800130E6
0x18001301b  mov     rax, cs:off_180049928; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180013022  test    rax, rax
0x180013025  jz      loc_1800130E6
0x18001302b  mov     r8, cs:off_180049928; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180013032  mov     edx, 53000h
0x180013037  mov     [rsp+68h+var_48], 14Ch
0x18001303f  jmp     loc_1800130D4
0x180013044  mov     ebp, dword ptr [rsp+68h+arg_0]
0x180013048  cmp     ebp, 0FFFFFFFFh
0x18001304b  jnz     loc_1800130F1
0x180013051  mov     ebp, [r15]
0x180013054  mov     rax, [rsi]
0x180013057  dec     ebp
0x180013059  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180013060  mov     ebx, ebp
0x180013062  shl     rbx, 5
0x180013066  movdqu  xmmword ptr [rbx+rax+0Ch], xmm0
0x18001306c  mov     rax, [rsi]
0x18001306f  mov     dword ptr [rbx+rax+8], 1
0x180013077  mov     rax, [rsi]
0x18001307a  mov     ecx, [rbx+rax+8]
0x18001307e  lea     rcx, [rcx+rcx*8]
0x180013082  shl     rcx, 3; cb
0x180013086  call    cs:__imp_CoTaskMemAlloc
0x18001308d  nop     dword ptr [rax+rax+00h]
0x180013092  mov     rcx, [rsi]
0x180013095  mov     [rbx+rcx], rax
0x180013099  mov     rax, [rsi]
0x18001309c  cmp     qword ptr [rbx+rax], 0
0x1800130a1  jnz     short loc_1800130F1
0x1800130a3  mov     dword ptr [rbx+rax+8], 0
0x1800130ab  test    byte ptr cs:_bidGblFlags, 2
0x1800130b2  jz      short loc_1800130E6
0x1800130b4  mov     rax, cs:off_180049918; "<CImpIColumnsRowset::SetupProperties|AD"...
0x1800130bb  test    rax, rax
0x1800130be  jz      short loc_1800130E6
0x1800130c0  mov     r8, cs:off_180049918; "<CImpIColumnsRowset::SetupProperties|AD"...
0x1800130c7  mov     edx, 5A000h
0x1800130cc  mov     [rsp+68h+var_48], 168h
0x1800130d4  mov     rcx, cs:off_1800491D0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800130db  mov     r9d, 8007000Eh
0x1800130e1  call    _bidTraceW
0x1800130e6  mov     ecx, 8007000Eh; int
0x1800130eb  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800130f1  test    r14d, r14d
0x1800130f4  jnz     short loc_180013157
0x1800130f6  mov     rcx, [rsi]
0x1800130f9  mov     edi, ebp
0x1800130fb  shl     rdi, 5
0x1800130ff  mov     eax, [rdi+rcx+8]
0x180013103  dec     eax
0x180013105  lea     rbx, [rax+rax*8]
0x180013109  mov     rax, [rdi+rcx]
0x18001310d  mov     dword ptr [rax+rbx*8], 86h
0x180013114  mov     rax, [rsi]
0x180013117  mov     rcx, [rdi+rax]
0x18001311b  mov     [rcx+rbx*8+4], r14d
0x180013120  mov     rax, [rsi]
0x180013123  mov     rcx, [rdi+rax]
0x180013127  lea     rcx, [rcx+rbx*8]
0x18001312b  add     rcx, 30h ; '0'; pvarg
0x18001312f  call    cs:__imp_VariantInit
0x180013136  nop     dword ptr [rax+rax+00h]
0x18001313b  mov     rax, [rsi]
0x18001313e  mov     rcx, [rdi+rax]
0x180013142  mov     word ptr [rcx+rbx*8+30h], 0Bh
0x180013149  mov     rax, [rsi]
0x18001314c  mov     rcx, [rdi+rax]
0x180013150  mov     word ptr [rcx+rbx*8+38h], 0FFFFh
0x180013157  mov     rbx, [rsp+68h+arg_8]
0x18001315c  add     rsp, 30h
0x180013160  pop     r15
0x180013162  pop     r14
0x180013164  pop     r13
0x180013166  pop     r12
0x180013168  pop     rdi
0x180013169  pop     rsi
0x18001316a  pop     rbp
0x18001316b  retn
```
