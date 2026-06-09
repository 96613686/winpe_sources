# UL_AND_WORKER_MANAGER::EnumerateAppPools(ulong *,ushort * * *,__MIDL_IW3Control_0001 * *,long * *)

- ea: `0x1800107bc`
- end: `0x180010a35`
- name: `?EnumerateAppPools@UL_AND_WORKER_MANAGER@@QEAAJPEAKPEAPEAPEAGPEAPEAW4__MIDL_IW3Control_0001@@PEAPEAJ@Z`
- size: `633`
- prototype: `__int64 __fastcall(UL_AND_WORKER_MANAGER *__hidden this, unsigned int *, unsigned __int16 ***, enum __MIDL_IW3Control_0001 **, int **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800322cc`

## callees

- `0x1800107bc`
- `0x180012a40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010825`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001087a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010825`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001087a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800109ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800109fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800109ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800109fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a2d`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180010894`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180010894`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x1800107f2`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010819`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010844`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18001086e`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x1800109a1`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x1800107f2`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010819`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010844`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18001086e`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x1800109a1`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x1800108a1`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180010962`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x1800108a1`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180010962`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x1800108ab`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18001096c`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010986`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010998`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x1800109e5`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x1800108ab`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18001096c`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010986`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010998`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x1800109e5`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180010955`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180010955`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18001097a`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18001097a`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180010948`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180010948`

## pseudocode

```c
__int64 __fastcall UL_AND_WORKER_MANAGER::EnumerateAppPools(
        UL_AND_WORKER_MANAGER *this,
        unsigned int *a2,
        unsigned __int16 ***a3,
        enum __MIDL_IW3Control_0001 **a4,
        int **a5)
{
  CLKRHashTable *v5; // r15
  unsigned __int16 **v9; // r14
  unsigned int v11; // eax
  int v12; // edi
  unsigned int v13; // r12d
  unsigned int v14; // eax
  int *v15; // r13
  unsigned __int16 **v16; // rsi
  unsigned int v17; // eax
  const struct CLKRHashTable_Iterator *v18; // rax
  __int64 v19; // rbx
  int v20; // eax
  SIZE_T v21; // rdi
  unsigned __int16 *v22; // rax
  __int64 v23; // rax
  const struct CLKRHashTable_Iterator *v24; // rax
  char v25; // bl
  __int64 i; // r15
  unsigned __int16 *v27; // [rsp+28h] [rbp-71h]
  _BYTE v28[16]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v29; // [rsp+40h] [rbp-59h]
  __int16 v30; // [rsp+4Ch] [rbp-4Dh]
  _BYTE v31[40]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v32[104]; // [rsp+80h] [rbp-19h] BYREF
  enum __MIDL_IW3Control_0001 *pv; // [rsp+F8h] [rbp+5Fh]

  v5 = (UL_AND_WORKER_MANAGER *)((char *)this + 16);
  v9 = 0;
  if ( !CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 16)) )
  {
    *a2 = 0;
    *a3 = 0;
    *a4 = 0;
    *a5 = 0;
    return 0;
  }
  v11 = CLKRHashTable::Size(v5);
  pv = (enum __MIDL_IW3Control_0001 *)CoTaskMemAlloc(4LL * v11);
  if ( pv )
  {
    v13 = 0;
    v14 = CLKRHashTable::Size(v5);
    v15 = (int *)CoTaskMemAlloc(4LL * v14);
    if ( v15 )
    {
      v17 = CLKRHashTable::Size(v5);
      v16 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v17);
      v9 = v16;
      if ( v16 )
      {
        v12 = 0;
        v18 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin(v5, v32);
        CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28, v18);
        CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v32);
        while ( 1 )
        {
          v24 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v5, v32);
          CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v31, v24);
          CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v32);
          v25 = CLKRHashTable_Iterator::operator!=(v28, v31);
          CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v31);
          if ( !v25 )
          {
            CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28);
            *a2 = CLKRHashTable::Size(v5);
            *a3 = v16;
            *a4 = pv;
            *a5 = v15;
            return (unsigned int)v12;
          }
          v19 = *(_QWORD *)(v29 + 8LL * v30 + 24);
          v15[v13] = *(_DWORD *)(v19 + 220);
          v20 = *(_DWORD *)(v19 + 20) == 3 ? 2 : (*(_DWORD *)(v19 + 20) != 4) + 3;
          *((_DWORD *)pv + v13) = v20;
          v21 = (unsigned int)(2 * *(_DWORD *)(v19 + 72) + 2);
          v22 = (unsigned __int16 *)CoTaskMemAlloc(v21);
          v27 = v22;
          if ( !v22 )
            break;
          v12 = StringCchCopyNW(
                  v22,
                  v21 >> 1,
                  *(const unsigned __int16 **)(v19 + 56),
                  (unsigned int)(*(_DWORD *)(v19 + 72) + 1));
          if ( v12 < 0 )
            goto LABEL_20;
          v23 = v13++;
          v16[v23] = v27;
          CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v28);
        }
        v12 = -2147024882;
LABEL_20:
        CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28);
        goto LABEL_21;
      }
    }
    else
    {
      v16 = 0;
    }
    v12 = -2147024882;
LABEL_21:
    CoTaskMemFree(pv);
    if ( v15 )
      CoTaskMemFree(v15);
    if ( v16 )
    {
      for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
      {
        CoTaskMemFree(v9[i]);
        v9[i] = 0;
      }
      CoTaskMemFree(v16);
    }
    return (unsigned int)v12;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1800107bc  mov     rax, rsp
0x1800107bf  mov     [rax+20h], r9
0x1800107c3  mov     [rax+18h], r8
0x1800107c7  mov     [rax+10h], rdx
0x1800107cb  push    rbp
0x1800107cc  push    rbx
0x1800107cd  push    rsi
0x1800107ce  push    rdi
0x1800107cf  push    r12
0x1800107d1  push    r13
0x1800107d3  push    r14
0x1800107d5  push    r15
0x1800107d7  lea     rbp, [rax-57h]
0x1800107db  sub     rsp, 0A8h
0x1800107e2  lea     r15, [rcx+10h]
0x1800107e6  mov     rbx, r9
0x1800107e9  mov     rcx, r15
0x1800107ec  mov     rdi, r8
0x1800107ef  mov     rsi, rdx
0x1800107f2  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x1800107f8  xor     r14d, r14d
0x1800107fb  test    eax, eax
0x1800107fd  jnz     short loc_180010816
0x1800107ff  mov     rax, [rbp+4Fh+arg_20]
0x180010803  mov     [rsi], r14d
0x180010806  mov     [rdi], r14
0x180010809  mov     [rbx], r14
0x18001080c  mov     [rax], r14
0x18001080f  xor     eax, eax
0x180010811  jmp     loc_1800109C8
0x180010816  mov     rcx, r15
0x180010819  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18001081f  mov     ecx, eax
0x180010821  shl     rcx, 2; cb
0x180010825  call    cs:__imp_CoTaskMemAlloc
0x18001082b  mov     [rbp+4Fh+pv], rax
0x18001082f  test    rax, rax
0x180010832  jnz     short loc_18001083E
0x180010834  mov     edi, 8007000Eh
0x180010839  jmp     loc_1800109C6
0x18001083e  mov     rcx, r15
0x180010841  mov     r12d, r14d
0x180010844  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18001084a  mov     ecx, eax
0x18001084c  shl     rcx, 2; cb
0x180010850  call    cs:__imp_CoTaskMemAlloc
0x180010856  mov     r13, rax
0x180010859  test    rax, rax
0x18001085c  jnz     short loc_18001086B
0x18001085e  mov     rsi, r14
0x180010861  mov     edi, 8007000Eh
0x180010866  jmp     loc_1800109EB
0x18001086b  mov     rcx, r15
0x18001086e  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180010874  mov     ecx, eax
0x180010876  shl     rcx, 3; cb
0x18001087a  call    cs:__imp_CoTaskMemAlloc
0x180010880  mov     rsi, rax
0x180010883  mov     r14, rax
0x180010886  test    rax, rax
0x180010889  jz      short loc_180010861
0x18001088b  lea     rdx, [rbp+4Fh+var_68]
0x18001088f  mov     rcx, r15
0x180010892  xor     edi, edi
0x180010894  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x18001089a  mov     rdx, rax
0x18001089d  lea     rcx, [rbp+4Fh+var_B8]
0x1800108a1  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x1800108a7  lea     rcx, [rbp+4Fh+var_68]
0x1800108ab  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x1800108b1  jmp     loc_18001094E
0x1800108b6  mov     rax, [rbp+4Fh+var_A8]
0x1800108ba  movsx   rcx, [rbp+4Fh+var_9C]
0x1800108bf  mov     edx, r12d
0x1800108c2  mov     rbx, [rax+rcx*8+18h]
0x1800108c7  mov     eax, [rbx+0DCh]
0x1800108cd  mov     [r13+rdx*4+0], eax
0x1800108d2  cmp     dword ptr [rbx+14h], 3
0x1800108d6  jnz     short loc_1800108DF
0x1800108d8  mov     eax, 2
0x1800108dd  jmp     short loc_1800108EB
0x1800108df  xor     eax, eax
0x1800108e1  cmp     dword ptr [rbx+14h], 4
0x1800108e5  setnz   al
0x1800108e8  add     eax, 3
0x1800108eb  mov     rcx, [rbp+4Fh+pv]
0x1800108ef  mov     [rcx+rdx*4], eax
0x1800108f2  mov     eax, [rbx+48h]
0x1800108f5  lea     eax, ds:2[rax*2]
0x1800108fc  mov     ecx, eax; cb
0x1800108fe  mov     edi, eax
0x180010900  call    cs:__imp_CoTaskMemAlloc
0x180010906  mov     [rbp+4Fh+var_C0], rax
0x18001090a  test    rax, rax
0x18001090d  jz      loc_1800109DC
0x180010913  mov     r9d, [rbx+48h]
0x180010917  mov     rcx, rax; unsigned __int16 *
0x18001091a  mov     r8, [rbx+38h]; unsigned __int16 *
0x18001091e  inc     r9d; unsigned __int64
0x180010921  shr     rdi, 1
0x180010924  mov     rdx, rdi; unsigned __int64
0x180010927  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001092c  mov     edi, eax
0x18001092e  test    eax, eax
0x180010930  js      loc_1800109E1
0x180010936  mov     rcx, [rbp+4Fh+var_C0]
0x18001093a  mov     eax, r12d
0x18001093d  inc     r12d
0x180010940  mov     [rsi+rax*8], rcx
0x180010944  lea     rcx, [rbp+4Fh+var_B8]
0x180010948  call    cs:__imp_?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x18001094e  lea     rdx, [rbp+4Fh+var_68]
0x180010952  mov     rcx, r15
0x180010955  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x18001095b  mov     rdx, rax
0x18001095e  lea     rcx, [rbp+4Fh+var_90]
0x180010962  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180010968  lea     rcx, [rbp+4Fh+var_68]
0x18001096c  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180010972  lea     rdx, [rbp+4Fh+var_90]
0x180010976  lea     rcx, [rbp+4Fh+var_B8]
0x18001097a  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x180010980  lea     rcx, [rbp+4Fh+var_90]
0x180010984  mov     bl, al
0x180010986  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18001098c  test    bl, bl
0x18001098e  jnz     loc_1800108B6
0x180010994  lea     rcx, [rbp+4Fh+var_B8]
0x180010998  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18001099e  mov     rcx, r15
0x1800109a1  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x1800109a7  mov     rcx, [rbp+4Fh+arg_8]
0x1800109ab  mov     [rcx], eax
0x1800109ad  mov     rax, [rbp+4Fh+arg_10]
0x1800109b1  mov     rcx, [rbp+4Fh+arg_18]
0x1800109b5  mov     [rax], rsi
0x1800109b8  mov     rax, [rbp+4Fh+pv]
0x1800109bc  mov     [rcx], rax
0x1800109bf  mov     rax, [rbp+4Fh+arg_20]
0x1800109c3  mov     [rax], r13
0x1800109c6  mov     eax, edi
0x1800109c8  add     rsp, 0A8h
0x1800109cf  pop     r15
0x1800109d1  pop     r14
0x1800109d3  pop     r13
0x1800109d5  pop     r12
0x1800109d7  pop     rdi
0x1800109d8  pop     rsi
0x1800109d9  pop     rbx
0x1800109da  pop     rbp
0x1800109db  retn
0x1800109dc  mov     edi, 8007000Eh
0x1800109e1  lea     rcx, [rbp+4Fh+var_B8]
0x1800109e5  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x1800109eb  mov     rcx, [rbp+4Fh+pv]; pv
0x1800109ef  call    cs:__imp_CoTaskMemFree
0x1800109f5  test    r13, r13
0x1800109f8  jz      short loc_180010A03
0x1800109fa  mov     rcx, r13; pv
0x1800109fd  call    cs:__imp_CoTaskMemFree
0x180010a03  test    rsi, rsi
0x180010a06  jz      short loc_1800109C6
0x180010a08  xor     r15d, r15d
0x180010a0b  test    r12d, r12d
0x180010a0e  jz      short loc_180010A2A
0x180010a10  mov     rcx, [r14+r15*8]; pv
0x180010a14  call    cs:__imp_CoTaskMemFree
0x180010a1a  mov     qword ptr [r14+r15*8], 0
0x180010a22  inc     r15d
0x180010a25  cmp     r15d, r12d
0x180010a28  jb      short loc_180010A10
0x180010a2a  mov     rcx, rsi; pv
0x180010a2d  call    cs:__imp_CoTaskMemFree
0x180010a33  jmp     short loc_1800109C6
```
