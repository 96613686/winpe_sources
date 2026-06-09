# CDPO::CopySpecificPropInfos(tagDBPROPIDSET const *,tagDBPROPINFOSET *,tagDBPROPINFOSET *,int *,int *)

- ea: `0x180067190`
- end: `0x180067412`
- name: `?CopySpecificPropInfos@CDPO@@AEAAJPEBUtagDBPROPIDSET@@PEAUtagDBPROPINFOSET@@1PEAH2@Z`
- size: `642`
- prototype: `__int64 __fastcall(CDPO *__hidden this, const struct tagDBPROPIDSET *, struct tagDBPROPINFOSET *, struct tagDBPROPINFOSET *, int *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180067420`

## callees

- `0x180013870`
- `0x180029560`
- `0x18002ec0c`
- `0x18002ec26`
- `0x180067190`
- `0x18007e6ca`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18006726f`
- `OLEAUT32!__imp_VariantInit` at `0x1800673af`
- `OLEAUT32!__imp_VariantInit` at `0x18006726f`
- `OLEAUT32!__imp_VariantInit` at `0x1800673af`
- `OLEAUT32!__imp_VariantCopy` at `0x180067286`
- `OLEAUT32!__imp_VariantCopy` at `0x1800673bd`
- `OLEAUT32!__imp_VariantCopy` at `0x180067286`
- `OLEAUT32!__imp_VariantCopy` at `0x1800673bd`
- `ole32!CoTaskMemAlloc` at `0x1800671c4`
- `ole32!CoTaskMemAlloc` at `0x1800672ad`
- `ole32!CoTaskMemAlloc` at `0x1800671c4`
- `ole32!CoTaskMemAlloc` at `0x1800672ad`

## string_xrefs

- `0x1800671ea`: `<CDPO::CopySpecificPropInfos|OLEDB|ERR> `
- `0x1800672d3`: `<CDPO::CopySpecificPropInfos|OLEDB|ERR> `
- `0x180067209`: `<CDPO::CopySpecificPropInfos|Trace|HR> `
- `0x1800672f2`: `<CDPO::CopySpecificPropInfos|Trace|HR> `
- `0x1800673e9`: `<CDPO::CopySpecificPropInfos|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDPO::CopySpecificPropInfos(
        CDPO *this,
        const struct tagDBPROPIDSET *a2,
        struct tagDBPROPINFOSET *a3,
        struct tagDBPROPINFOSET *a4,
        int *a5,
        int *a6)
{
  DBPROPINFO *v9; // rax
  int v10; // ebx
  __int64 i; // rbp
  PDBPROPINFO v12; // rbx
  DBPROPINFO *v13; // rax
  int v14; // ebx
  ULONG cPropertyIDs; // eax
  int *v16; // r12
  __int64 v17; // rdi
  int *v18; // r13
  PDBPROPINFO rgPropertyInfos; // r9
  __int64 v20; // rdx
  DBPROPID v21; // r10d
  DBPROPINFO *v22; // rbp
  DBPROPINFO *v23; // rbx
  CDPO *pExceptionObject; // [rsp+70h] [rbp+8h] BYREF

  pExceptionObject = this;
  if ( a2->cPropertyIDs )
  {
    v13 = (DBPROPINFO *)CoTaskMemAlloc(48LL * a2->cPropertyIDs);
    a3->rgPropertyInfos = v13;
    if ( !v13 )
    {
      v14 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024882, L"<CDPO::CopySpecificPropInfos|OLEDB|ERR> ", 0xAEu);
        if ( (bidGblFlags & 2) != 0 )
          v14 = bidTraceHR(off_1800C8450[0], 178185, L"<CDPO::CopySpecificPropInfos|Trace|HR> ", 2147942414LL);
      }
      LODWORD(pExceptionObject) = v14;
      throw (long *)&pExceptionObject;
    }
    memset_0(v13, 0, 48LL * a2->cPropertyIDs);
    cPropertyIDs = a2->cPropertyIDs;
    a3->cPropertyInfos = cPropertyIDs;
    if ( cPropertyIDs )
    {
      v16 = a6;
      v17 = 0;
      v18 = a5;
      do
      {
        rgPropertyInfos = a3->rgPropertyInfos;
        v20 = 0;
        v21 = a2->rgPropertyIDs[v17];
        a3->rgPropertyInfos[v17].dwPropertyID = v21;
        while ( (unsigned int)v20 < a4->cPropertyInfos )
        {
          v22 = &a4->rgPropertyInfos[v20];
          if ( v22->dwPropertyID == v21 )
          {
            if ( v22 )
            {
              v23 = &rgPropertyInfos[v17];
              *(_OWORD *)&v23->pwszDescription = *(_OWORD *)&v22->pwszDescription;
              *(_OWORD *)&v23->vtType = *(_OWORD *)&v22->vtType;
              *(_OWORD *)&v23->vValues.decVal.Lo32 = *(_OWORD *)&v22->vValues.decVal.Lo32;
              VariantInit(&v23->vValues);
              VariantCopy(&v23->vValues, &v22->vValues);
              ++*v18;
              goto LABEL_24;
            }
            break;
          }
          v20 = (unsigned int)(v20 + 1);
        }
        ++*v16;
LABEL_24:
        v17 = (unsigned int)(v17 + 1);
      }
      while ( (unsigned int)v17 < a3->cPropertyInfos );
    }
  }
  else
  {
    v9 = (DBPROPINFO *)CoTaskMemAlloc(48LL * a4->cPropertyInfos);
    a3->rgPropertyInfos = v9;
    if ( !v9 )
    {
      v10 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024882, L"<CDPO::CopySpecificPropInfos|OLEDB|ERR> ", 0x9Au);
        if ( (bidGblFlags & 2) != 0 )
          v10 = bidTraceHR(off_1800C8450[0], 157705, L"<CDPO::CopySpecificPropInfos|Trace|HR> ", 2147942414LL);
      }
      LODWORD(pExceptionObject) = v10;
      throw (long *)&pExceptionObject;
    }
    a3->cPropertyInfos = a4->cPropertyInfos;
    memcpy_0(v9, a4->rgPropertyInfos, 48LL * a4->cPropertyInfos);
    for ( i = 0; (unsigned int)i < a4->cPropertyInfos; i = (unsigned int)(i + 1) )
    {
      v12 = a3->rgPropertyInfos;
      VariantInit(&a3->rgPropertyInfos[i].vValues);
      VariantCopy(&v12[i].vValues, &a4->rgPropertyInfos[i].vValues);
    }
    ++*a5;
  }
  if ( (bidGblFlags & 2) != 0 )
    return bidTraceHR(off_1800C8450[0], 216073, L"<CDPO::CopySpecificPropInfos|Trace|HR> ", 0);
  else
    return 0;
}

```

## disassembly

```asm
0x180067190  mov     [rsp+pExceptionObject], rcx
0x180067195  push    rbx
0x180067196  push    rbp
0x180067197  push    rsi
0x180067198  push    rdi
0x180067199  push    r12
0x18006719b  push    r13
0x18006719d  push    r14
0x18006719f  push    r15
0x1800671a1  sub     rsp, 28h
0x1800671a5  cmp     dword ptr [rdx+8], 0
0x1800671a9  mov     rsi, r9
0x1800671ac  mov     r14, r8
0x1800671af  mov     r15, rdx
0x1800671b2  jnz     loc_1800672A2
0x1800671b8  mov     eax, [r9+8]
0x1800671bc  lea     rcx, [rax+rax*2]
0x1800671c0  shl     rcx, 4; cb
0x1800671c4  call    cs:__imp_CoTaskMemAlloc
0x1800671ca  mov     [r14], rax
0x1800671cd  mov     rcx, rax; void *
0x1800671d0  test    rax, rax
0x1800671d3  jnz     short loc_180067235
0x1800671d5  mov     eax, cs:_bidGblFlags
0x1800671db  mov     ebx, 8007000Eh
0x1800671e0  test    al, 2
0x1800671e2  jz      short loc_18006721F
0x1800671e4  mov     r8d, 9Ah; unsigned int
0x1800671ea  lea     rdx, aCdpoCopyspecif; "<CDPO::CopySpecificPropInfos|OLEDB|ERR>"...
0x1800671f1  mov     ecx, ebx; int
0x1800671f3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800671f8  mov     eax, cs:_bidGblFlags
0x1800671fe  test    al, 2
0x180067200  jz      short loc_18006721F
0x180067202  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180067209  lea     r8, aCdpoCopyspecif_0; "<CDPO::CopySpecificPropInfos|Trace|HR> "
0x180067210  mov     r9d, ebx
0x180067213  mov     edx, 26809h
0x180067218  call    _bidTraceHR
0x18006721d  mov     ebx, eax
0x18006721f  lea     rdx, _TI1J; pThrowInfo
0x180067226  mov     dword ptr [rsp+68h+pExceptionObject], ebx
0x18006722a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18006722f  call    _CxxThrowException_0
0x180067235  mov     eax, [rsi+8]
0x180067238  mov     [r14+8], eax
0x18006723c  mov     eax, [rsi+8]
0x18006723f  mov     rdx, [rsi]; Src
0x180067242  lea     r8, [rax+rax*2]
0x180067246  shl     r8, 4; Size
0x18006724a  call    memcpy_0
0x18006724f  xor     ebp, ebp
0x180067251  cmp     [rsi+8], ebp
0x180067254  jbe     short loc_180067293
0x180067256  mov     rbx, [r14]
0x180067259  lea     rdi, ds:0[rbp*2]
0x180067261  add     rdi, rbp
0x180067264  shl     rdi, 4
0x180067268  lea     rcx, [rbx+18h]
0x18006726c  add     rcx, rdi; pvarg
0x18006726f  call    cs:__imp_VariantInit
0x180067275  mov     rdx, [rsi]
0x180067278  lea     rcx, [rbx+18h]
0x18006727c  add     rdx, 18h
0x180067280  add     rcx, rdi; pvargDest
0x180067283  add     rdx, rdi; pvargSrc
0x180067286  call    cs:__imp_VariantCopy
0x18006728c  inc     ebp
0x18006728e  cmp     ebp, [rsi+8]
0x180067291  jb      short loc_180067256
0x180067293  mov     rax, [rsp+68h+arg_20]
0x18006729b  inc     dword ptr [rax]
0x18006729d  jmp     loc_1800673D9
0x1800672a2  mov     eax, [rdx+8]
0x1800672a5  lea     rcx, [rax+rax*2]
0x1800672a9  shl     rcx, 4; cb
0x1800672ad  call    cs:__imp_CoTaskMemAlloc
0x1800672b3  mov     [r14], rax
0x1800672b6  mov     rcx, rax; void *
0x1800672b9  test    rax, rax
0x1800672bc  jnz     short loc_18006731E
0x1800672be  mov     eax, cs:_bidGblFlags
0x1800672c4  mov     ebx, 8007000Eh
0x1800672c9  test    al, 2
0x1800672cb  jz      short loc_180067308
0x1800672cd  mov     r8d, 0AEh; unsigned int
0x1800672d3  lea     rdx, aCdpoCopyspecif; "<CDPO::CopySpecificPropInfos|OLEDB|ERR>"...
0x1800672da  mov     ecx, ebx; int
0x1800672dc  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800672e1  mov     eax, cs:_bidGblFlags
0x1800672e7  test    al, 2
0x1800672e9  jz      short loc_180067308
0x1800672eb  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800672f2  lea     r8, aCdpoCopyspecif_0; "<CDPO::CopySpecificPropInfos|Trace|HR> "
0x1800672f9  mov     r9d, ebx
0x1800672fc  mov     edx, 2B809h
0x180067301  call    _bidTraceHR
0x180067306  mov     ebx, eax
0x180067308  lea     rdx, _TI1J; pThrowInfo
0x18006730f  mov     dword ptr [rsp+68h+pExceptionObject], ebx
0x180067313  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180067318  call    _CxxThrowException_0
0x18006731e  mov     eax, [r15+8]
0x180067322  xor     edx, edx; Val
0x180067324  lea     r8, [rax+rax*2]
0x180067328  shl     r8, 4; Size
0x18006732c  call    memset_0
0x180067331  mov     eax, [r15+8]
0x180067335  mov     [r14+8], eax
0x180067339  test    eax, eax
0x18006733b  jz      loc_1800673D9
0x180067341  mov     r12, [rsp+68h+arg_28]
0x180067349  xor     edi, edi
0x18006734b  mov     r13, [rsp+68h+arg_20]
0x180067353  mov     rax, [r15]
0x180067356  lea     r8, [rdi+rdi*2]
0x18006735a  mov     r9, [r14]
0x18006735d  add     r8, r8
0x180067360  xor     edx, edx
0x180067362  mov     r10d, [rax+rdi*4]
0x180067366  mov     [r9+r8*8+8], r10d
0x18006736b  cmp     edx, [rsi+8]
0x18006736e  jnb     short loc_1800673C9
0x180067370  lea     rbp, [rdx+rdx*2]
0x180067374  shl     rbp, 4
0x180067378  add     rbp, [rsi]
0x18006737b  cmp     [rbp+8], r10d
0x18006737f  jz      short loc_180067385
0x180067381  inc     edx
0x180067383  jmp     short loc_18006736B
0x180067385  test    rbp, rbp
0x180067388  jz      short loc_1800673C9
0x18006738a  movups  xmm0, xmmword ptr [rbp+0]
0x18006738e  lea     rbx, [r9+r8*8]
0x180067392  lea     rcx, [rbx+18h]; pvarg
0x180067396  movups  xmmword ptr [r9+r8*8], xmm0
0x18006739b  movups  xmm1, xmmword ptr [rbp+10h]
0x18006739f  movups  xmmword ptr [r9+r8*8+10h], xmm1
0x1800673a5  movups  xmm0, xmmword ptr [rbp+20h]
0x1800673a9  movups  xmmword ptr [r9+r8*8+20h], xmm0
0x1800673af  call    cs:__imp_VariantInit
0x1800673b5  lea     rdx, [rbp+18h]; pvargSrc
0x1800673b9  lea     rcx, [rbx+18h]; pvargDest
0x1800673bd  call    cs:__imp_VariantCopy
0x1800673c3  inc     dword ptr [r13+0]
0x1800673c7  jmp     short loc_1800673CD
0x1800673c9  inc     dword ptr [r12]
0x1800673cd  inc     edi
0x1800673cf  cmp     edi, [r14+8]
0x1800673d3  jb      loc_180067353
0x1800673d9  test    byte ptr cs:_bidGblFlags, 2
0x1800673e0  jz      short loc_1800673FF
0x1800673e2  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800673e9  lea     r8, aCdpoCopyspecif_0; "<CDPO::CopySpecificPropInfos|Trace|HR> "
0x1800673f0  xor     r9d, r9d
0x1800673f3  mov     edx, 34C09h
0x1800673f8  call    _bidTraceHR
0x1800673fd  jmp     short loc_180067401
0x1800673ff  xor     eax, eax
0x180067401  add     rsp, 28h
0x180067405  pop     r15
0x180067407  pop     r14
0x180067409  pop     r13
0x18006740b  pop     r12
0x18006740d  pop     rdi
0x18006740e  pop     rsi
0x18006740f  pop     rbp
0x180067410  pop     rbx
0x180067411  retn
```
