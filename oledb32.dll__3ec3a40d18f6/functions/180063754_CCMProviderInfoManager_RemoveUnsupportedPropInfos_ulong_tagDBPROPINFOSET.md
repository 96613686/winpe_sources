# CCMProviderInfoManager::RemoveUnsupportedPropInfos(ulong *,tagDBPROPINFOSET * *)

- ea: `0x180063754`
- end: `0x180063a8d`
- name: `?RemoveUnsupportedPropInfos@CCMProviderInfoManager@@CAJPEAKPEAPEAUtagDBPROPINFOSET@@@Z`
- size: `825`
- prototype: `__int64 __fastcall(unsigned int *, struct tagDBPROPINFOSET **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18001d6d8`

## callees

- `0x180013870`
- `0x180029560`
- `0x180063754`
- `0x180077138`
- `0x18007e6ca`
- `0x18007e700`
- `0x18007e7c0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18006397a`
- `OLEAUT32!__imp_VariantInit` at `0x18006397a`
- `OLEAUT32!__imp_VariantClear` at `0x180063a29`
- `OLEAUT32!__imp_VariantClear` at `0x180063a29`
- `OLEAUT32!__imp_VariantCopy` at `0x180063993`
- `OLEAUT32!__imp_VariantCopy` at `0x180063993`
- `ole32!CoTaskMemAlloc` at `0x18006382d`
- `ole32!CoTaskMemAlloc` at `0x1800638ec`
- `ole32!CoTaskMemAlloc` at `0x18006382d`
- `ole32!CoTaskMemAlloc` at `0x1800638ec`
- `ole32!CoTaskMemFree` at `0x180063a3d`
- `ole32!CoTaskMemFree` at `0x180063a51`
- `ole32!CoTaskMemFree` at `0x180063a3d`
- `ole32!CoTaskMemFree` at `0x180063a51`

## string_xrefs

- `0x180063850`: `<CCMProviderInfoManager::RemoveUnsupportedPropInfos|OLEDB|ERR> `
- `0x1800639e5`: `<CCMProviderInfoManager::RemoveUnsupportedPropInfos|OLEDB|ERR> `
- `0x18006386f`: `<CCMProviderInfoManager::RemoveUnsupportedPropInfos|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CCMProviderInfoManager::RemoveUnsupportedPropInfos(unsigned int *a1, struct tagDBPROPINFOSET **a2)
{
  size_t v2; // r8
  struct tagDBPROPINFOSET **v3; // rsi
  unsigned int v5; // r14d
  __int64 v6; // rax
  void *v7; // rsp
  unsigned int v8; // ecx
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  __int64 v11; // rdx
  struct tagDBPROPINFOSET *v12; // rax
  struct tagDBPROPINFOSET *v13; // rdi
  unsigned int v14; // esi
  __int64 result; // rax
  unsigned int v16; // edx
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r15
  size_t v21; // rbx
  GUID v22; // xmm0
  DBPROPINFO *v23; // rax
  __int64 v24; // rcx
  __int64 i; // rax
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rbx
  unsigned int v31; // r8d
  unsigned int v32; // r12d
  __int64 v33; // r13
  __int64 v34; // rbx
  __int64 j; // r15
  int v36; // [rsp+20h] [rbp+0h] BYREF
  int v37; // [rsp+24h] [rbp+4h]
  int v38; // [rsp+28h] [rbp+8h]
  unsigned int v39; // [rsp+2Ch] [rbp+Ch]
  __int64 v40; // [rsp+30h] [rbp+10h]
  __int64 v41; // [rsp+38h] [rbp+18h]
  __int64 v42; // [rsp+40h] [rbp+20h]
  struct tagDBPROPINFOSET **v43; // [rsp+48h] [rbp+28h]

  v2 = 4LL * *a1;
  v3 = a2;
  v43 = a2;
  v5 = 0;
  v6 = v2 + 15;
  if ( v2 + 15 < v2 )
    v6 = 0xFFFFFFFFFFFFFF0LL;
  v7 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
  memset_0(&v36, 0, v2);
  v8 = *a1;
  v9 = 0;
  if ( !*a1 )
    goto LABEL_42;
  do
  {
    v10 = 0;
    v11 = (__int64)&(*v3)[v9];
    if ( *(_DWORD *)(v11 + 8) )
    {
      do
      {
        if ( *(_DWORD *)(*(_QWORD *)v11 + 48LL * v10 + 12) )
          ++*(&v36 + v9);
        ++v10;
      }
      while ( v10 < *(_DWORD *)(v11 + 8) );
    }
    if ( *(&v36 + v9) )
      ++v5;
    v8 = *a1;
    ++v9;
  }
  while ( v9 < *a1 );
  if ( !v5 )
  {
LABEL_42:
    v13 = 0;
LABEL_43:
    FreePropInfoSets(v8, *v3);
    *a1 = v5;
    result = 0;
    *v3 = v13;
    return result;
  }
  v12 = (struct tagDBPROPINFOSET *)CoTaskMemAlloc(32LL * v5);
  v13 = v12;
  if ( v12 )
  {
    memset_0(v12, 0, 32LL * v5);
    v16 = 0;
    v17 = 0;
    v38 = 0;
    while ( 1 )
    {
      v8 = *a1;
      v39 = v17;
      if ( v17 >= v8 )
        goto LABEL_43;
      v18 = (unsigned int)*(&v36 + v17);
      if ( (_DWORD)v18 )
      {
        v19 = v16;
        v40 = v19 * 32;
        v20 = (__int64)&(*v3)[v17];
        v21 = 48 * v18;
        v22 = *(GUID *)(v20 + 12);
        v13[v19].cPropertyInfos = v18;
        v13[v19].guidPropertySet = v22;
        v23 = (DBPROPINFO *)CoTaskMemAlloc(48 * v18);
        v14 = -2147024882;
        *(PDBPROPINFO *)((char *)&v13->rgPropertyInfos + v40) = v23;
        if ( v23 )
        {
          memset_0(v23, 0, v21);
          v24 = 0;
          v36 = 0;
          for ( i = 0; ; i = (unsigned int)(v37 + 1) )
          {
            v37 = i;
            if ( (unsigned int)i >= *(_DWORD *)(v20 + 8) )
            {
              v17 = v39;
              v16 = v38 + 1;
              v3 = v43;
              ++v38;
              goto LABEL_28;
            }
            v26 = *(_QWORD *)v20;
            v27 = 48 * i;
            v41 = 48 * i;
            v42 = v26;
            if ( *(_DWORD *)(48 * i + v26 + 12) )
            {
              v28 = 6 * v24;
              v29 = *(__int64 *)((char *)&v13->rgPropertyInfos + v40);
              *(_OWORD *)(v29 + 8 * v28) = *(_OWORD *)(v27 + v26);
              v30 = v29 + 8 * v28;
              *(_OWORD *)(v30 + 16) = *(_OWORD *)(v27 + v26 + 16);
              *(_OWORD *)(v30 + 32) = *(_OWORD *)(v27 + v26 + 32);
              VariantInit((VARIANTARG *)(v30 + 24));
              if ( VariantCopy((VARIANTARG *)(v30 + 24), (const VARIANTARG *)(v41 + 24 + v42)) < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  v31 = 303;
                  goto LABEL_33;
                }
                goto LABEL_34;
              }
              v24 = (unsigned int)++v36;
            }
          }
        }
        if ( (bidGblFlags & 2) != 0 )
        {
          v31 = 282;
LABEL_33:
          OLEDBTraceErr(-2147024882, L"<CCMProviderInfoManager::RemoveUnsupportedPropInfos|OLEDB|ERR> ", v31);
        }
LABEL_34:
        v32 = 0;
        v33 = 0;
        do
        {
          v34 = v33;
          if ( v13[v33].rgPropertyInfos )
          {
            for ( j = 0; (unsigned int)j < v13[v34].cPropertyInfos; j = (unsigned int)(j + 1) )
              VariantClear(&v13[v34].rgPropertyInfos[j].vValues);
            CoTaskMemFree(v13[v34].rgPropertyInfos);
          }
          ++v32;
          ++v33;
        }
        while ( v32 < v5 );
        CoTaskMemFree(v13);
        return v14;
      }
LABEL_28:
      ++v17;
    }
  }
  v14 = -2147024882;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147024882, L"<CCMProviderInfoManager::RemoveUnsupportedPropInfos|OLEDB|ERR> ", 0x102u);
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(
                             off_1800C8438[0],
                             264201,
                             L"<CCMProviderInfoManager::RemoveUnsupportedPropInfos|Trace|HR> ",
                             2147942414LL);
  }
  return v14;
}

```

## disassembly

```asm
0x180063754  push    rbp
0x180063756  push    rbx
0x180063757  push    rsi
0x180063758  push    rdi
0x180063759  push    r12
0x18006375b  push    r13
0x18006375d  push    r14
0x18006375f  push    r15
0x180063761  sub     rsp, 68h
0x180063765  lea     rbp, [rsp+20h]
0x18006376a  mov     rax, cs:__security_cookie
0x180063771  xor     rax, rbp
0x180063774  mov     [rbp+80h+var_50], rax
0x180063778  mov     r8d, [rcx]
0x18006377b  xor     r15d, r15d
0x18006377e  shl     r8, 2
0x180063782  mov     rsi, rdx
0x180063785  mov     [rbp+80h+var_58], rdx
0x180063789  mov     r12, rcx
0x18006378c  mov     r14d, r15d
0x18006378f  lea     rax, [r8+0Fh]
0x180063793  cmp     rax, r8
0x180063796  ja      short loc_1800637A2
0x180063798  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800637a2  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800637a6  call    _alloca_probe
0x1800637ab  sub     rsp, rax
0x1800637ae  xor     edx, edx; Val
0x1800637b0  lea     r13, [rsp+0A0h+var_80]
0x1800637b5  mov     rcx, r13; void *
0x1800637b8  call    memset_0
0x1800637bd  mov     ecx, [r12]; unsigned int
0x1800637c1  mov     r8d, r15d
0x1800637c4  test    ecx, ecx
0x1800637c6  jz      loc_180063A5C
0x1800637cc  mov     edx, r8d
0x1800637cf  mov     r9d, r15d
0x1800637d2  shl     rdx, 5
0x1800637d6  add     rdx, [rsi]
0x1800637d9  mov     r10d, r8d
0x1800637dc  cmp     [rdx+8], r15d
0x1800637e0  jbe     short loc_180063804
0x1800637e2  mov     eax, r9d
0x1800637e5  lea     rcx, [rax+rax*2]
0x1800637e9  mov     rax, [rdx]
0x1800637ec  add     rcx, rcx
0x1800637ef  cmp     [rax+rcx*8+0Ch], r15d
0x1800637f4  jz      short loc_1800637FB
0x1800637f6  inc     dword ptr [r13+r10*4+0]
0x1800637fb  inc     r9d
0x1800637fe  cmp     r9d, [rdx+8]
0x180063802  jb      short loc_1800637E2
0x180063804  cmp     [r13+r10*4+0], r15d
0x180063809  jz      short loc_18006380E
0x18006380b  inc     r14d
0x18006380e  mov     ecx, [r12]
0x180063812  inc     r8d
0x180063815  cmp     r8d, ecx
0x180063818  jb      short loc_1800637CC
0x18006381a  test    r14d, r14d
0x18006381d  jz      loc_180063A5C
0x180063823  mov     ebx, r14d
0x180063826  shl     rbx, 5
0x18006382a  mov     rcx, rbx; cb
0x18006382d  call    cs:__imp_CoTaskMemAlloc
0x180063833  mov     rdi, rax
0x180063836  test    rax, rax
0x180063839  jnz     short loc_18006388C
0x18006383b  mov     eax, cs:_bidGblFlags
0x180063841  mov     esi, 8007000Eh
0x180063846  test    al, 2
0x180063848  jz      short loc_180063885
0x18006384a  mov     r8d, 102h; unsigned int
0x180063850  lea     rdx, aCcmproviderinf_7; "<CCMProviderInfoManager::RemoveUnsuppor"...
0x180063857  mov     ecx, esi; int
0x180063859  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006385e  mov     eax, cs:_bidGblFlags
0x180063864  test    al, 2
0x180063866  jz      short loc_180063885
0x180063868  mov     rcx, cs:off_1800C8438; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006386f  lea     r8, aCcmproviderinf_9; "<CCMProviderInfoManager::RemoveUnsuppor"...
0x180063876  mov     r9d, esi
0x180063879  mov     edx, 40809h
0x18006387e  call    _bidTraceHR
0x180063883  mov     esi, eax
0x180063885  mov     eax, esi
0x180063887  jmp     loc_180063A70
0x18006388c  mov     r8, rbx; Size
0x18006388f  xor     edx, edx; Val
0x180063891  mov     rcx, rdi; void *
0x180063894  call    memset_0
0x180063899  mov     edx, r15d
0x18006389c  mov     ebx, r15d
0x18006389f  mov     [rbp+80h+var_78], edx
0x1800638a2  mov     ecx, [r12]
0x1800638a6  mov     [rbp+80h+var_74], ebx
0x1800638a9  cmp     ebx, ecx
0x1800638ab  jnb     loc_180063A5F
0x1800638b1  mov     r15d, ebx
0x1800638b4  mov     eax, [r13+r15*4+0]
0x1800638b9  test    eax, eax
0x1800638bb  jz      loc_1800639BE
0x1800638c1  mov     ecx, edx
0x1800638c3  lea     rbx, [rax+rax*2]
0x1800638c7  shl     rcx, 5
0x1800638cb  mov     [rbp+80h+var_70], rcx
0x1800638cf  shl     r15, 5
0x1800638d3  add     r15, [rsi]
0x1800638d6  shl     rbx, 4
0x1800638da  movups  xmm0, xmmword ptr [r15+0Ch]
0x1800638df  mov     [rcx+rdi+8], eax
0x1800638e3  movdqu  xmmword ptr [rcx+rdi+0Ch], xmm0
0x1800638e9  mov     rcx, rbx; cb
0x1800638ec  call    cs:__imp_CoTaskMemAlloc
0x1800638f2  mov     rcx, [rbp+80h+var_70]
0x1800638f6  mov     esi, 8007000Eh
0x1800638fb  mov     [rcx+rdi], rax
0x1800638ff  test    rax, rax
0x180063902  jz      loc_1800639D6
0x180063908  mov     r8, rbx; Size
0x18006390b  xor     edx, edx; Val
0x18006390d  mov     rcx, rax; void *
0x180063910  call    memset_0
0x180063915  xor     ecx, ecx
0x180063917  mov     [rbp+80h+var_80], ecx
0x18006391a  xor     eax, eax
0x18006391c  mov     [rbp+80h+var_7C], eax
0x18006391f  cmp     eax, [r15+8]
0x180063923  jnb     loc_1800639AF
0x180063929  mov     r8, [r15]
0x18006392c  lea     rdx, [rax+rax*2]
0x180063930  shl     rdx, 4
0x180063934  mov     [rbp+80h+var_68], rdx
0x180063938  mov     [rbp+80h+var_60], r8
0x18006393c  cmp     dword ptr [rdx+r8+0Ch], 0
0x180063942  jz      short loc_1800639A5
0x180063944  movups  xmm0, xmmword ptr [rdx+r8]
0x180063949  mov     rax, [rbp+80h+var_70]
0x18006394d  lea     rcx, [rcx+rcx*2]
0x180063951  add     rcx, rcx
0x180063954  mov     rax, [rax+rdi]
0x180063958  movups  xmmword ptr [rax+rcx*8], xmm0
0x18006395c  lea     rbx, [rax+rcx*8]
0x180063960  movups  xmm1, xmmword ptr [rdx+r8+10h]
0x180063966  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x18006396b  movups  xmm0, xmmword ptr [rdx+r8+20h]
0x180063971  movups  xmmword ptr [rax+rcx*8+20h], xmm0
0x180063976  lea     rcx, [rbx+18h]; pvarg
0x18006397a  call    cs:__imp_VariantInit
0x180063980  mov     rax, [rbp+80h+var_68]
0x180063984  lea     rcx, [rbx+18h]; pvargDest
0x180063988  mov     rdx, [rbp+80h+var_60]
0x18006398c  add     rax, 18h
0x180063990  add     rdx, rax; pvargSrc
0x180063993  call    cs:__imp_VariantCopy
0x180063999  test    eax, eax
0x18006399b  js      short loc_1800639C5
0x18006399d  mov     ecx, [rbp+80h+var_80]
0x1800639a0  inc     ecx
0x1800639a2  mov     [rbp+80h+var_80], ecx
0x1800639a5  mov     eax, [rbp+80h+var_7C]
0x1800639a8  inc     eax
0x1800639aa  jmp     loc_18006391C
0x1800639af  mov     edx, [rbp+80h+var_78]
0x1800639b2  mov     ebx, [rbp+80h+var_74]
0x1800639b5  inc     edx
0x1800639b7  mov     rsi, [rbp+80h+var_58]
0x1800639bb  mov     [rbp+80h+var_78], edx
0x1800639be  inc     ebx
0x1800639c0  jmp     loc_1800638A2
0x1800639c5  test    byte ptr cs:_bidGblFlags, 2
0x1800639cc  jz      short loc_1800639F3
0x1800639ce  mov     r8d, 12Fh
0x1800639d4  jmp     short loc_1800639E5
0x1800639d6  test    byte ptr cs:_bidGblFlags, 2
0x1800639dd  jz      short loc_1800639F3
0x1800639df  mov     r8d, 11Ah; unsigned int
0x1800639e5  lea     rdx, aCcmproviderinf_7; "<CCMProviderInfoManager::RemoveUnsuppor"...
0x1800639ec  mov     ecx, esi; int
0x1800639ee  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800639f3  xor     r12d, r12d
0x1800639f6  test    r14d, r14d
0x1800639f9  jz      short loc_180063A4E
0x1800639fb  xor     r13d, r13d
0x1800639fe  mov     rbx, r13
0x180063a01  shl     rbx, 5
0x180063a05  cmp     qword ptr [rbx+rdi], 0
0x180063a0a  jz      short loc_180063A43
0x180063a0c  xor     r15d, r15d
0x180063a0f  cmp     [rbx+rdi+8], r15d
0x180063a14  jbe     short loc_180063A39
0x180063a16  mov     rax, [rbx+rdi]
0x180063a1a  lea     rcx, [r15+r15*2]
0x180063a1e  shl     rcx, 4
0x180063a22  add     rax, 18h
0x180063a26  add     rcx, rax; pvarg
0x180063a29  call    cs:__imp_VariantClear
0x180063a2f  inc     r15d
0x180063a32  cmp     r15d, [rbx+rdi+8]
0x180063a37  jb      short loc_180063A16
0x180063a39  mov     rcx, [rbx+rdi]; pv
0x180063a3d  call    cs:__imp_CoTaskMemFree
0x180063a43  inc     r12d
0x180063a46  inc     r13
0x180063a49  cmp     r12d, r14d
0x180063a4c  jb      short loc_1800639FE
0x180063a4e  mov     rcx, rdi; pv
0x180063a51  call    cs:__imp_CoTaskMemFree
0x180063a57  jmp     loc_180063885
0x180063a5c  mov     rdi, r15
0x180063a5f  mov     rdx, [rsi]; struct tagDBPROPINFOSET *
0x180063a62  call    ?FreePropInfoSets@@YAXKPEAUtagDBPROPINFOSET@@@Z; FreePropInfoSets(ulong,tagDBPROPINFOSET *)
0x180063a67  mov     [r12], r14d
0x180063a6b  xor     eax, eax
0x180063a6d  mov     [rsi], rdi
0x180063a70  mov     rcx, [rbp+80h+var_50]
0x180063a74  xor     rcx, rbp; StackCookie
0x180063a77  call    __security_check_cookie
0x180063a7c  lea     rsp, [rbp+48h]
0x180063a80  pop     r15
0x180063a82  pop     r14
0x180063a84  pop     r13
0x180063a86  pop     r12
0x180063a88  pop     rdi
0x180063a89  pop     rsi
0x180063a8a  pop     rbx
0x180063a8b  pop     rbp
0x180063a8c  retn
```
