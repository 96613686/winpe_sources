# CDataConvert::GetInfo(ulong,ulong * const,tagDCINFO * *)

- ea: `0x18003f2d0`
- end: `0x18003f410`
- name: `?GetInfo@CDataConvert@@UEAAJKQEAKPEAPEAUtagDCINFO@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(CDataConvert *__hidden this, unsigned int, unsigned int *const, struct tagDCINFO **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180013870`
- `0x180029560`
- `0x18003f2d0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003f384`
- `OLEAUT32!__imp_VariantInit` at `0x18003f384`
- `ole32!CoTaskMemAlloc` at `0x18003f30c`
- `ole32!CoTaskMemAlloc` at `0x18003f30c`

## pseudocode

```c
__int64 __fastcall CDataConvert::GetInfo(
        CDataConvert *this,
        unsigned int a2,
        unsigned int *const a3,
        struct tagDCINFO **a4)
{
  struct tagDCINFO *v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  unsigned int v12; // ebp
  __int64 v13; // rdi
  VARIANT *p_vData; // rcx

  if ( !a2 || !a3 )
  {
    if ( a4 )
      *a4 = 0;
    v10 = -2147024809;
    if ( (bidGblFlags & 2) == 0 )
      return v10;
    OLEDBTraceErr(-2147024809, L"<CDataConvert::GetInfo|OLEDB|ERR> ", 0x2363u);
    if ( (bidGblFlags & 2) == 0 )
      return v10;
    v11 = 9277449;
    return (unsigned int)bidTraceHR(off_1800C8390[0], v11, L"<CDataConvert::GetInfo|Trace|HR> ", v10);
  }
  if ( !a4 )
    return 0;
  v9 = (struct tagDCINFO *)CoTaskMemAlloc(32LL * a2);
  *a4 = v9;
  if ( v9 )
  {
    v12 = 0;
    if ( a2 )
    {
      v13 = 0;
      do
      {
        (*a4)[v13].eInfoType = a3[v13];
        p_vData = &(*a4)[v13].vData;
        if ( a3[v13] == 1 )
        {
          p_vData->vt = 19;
          (*a4)[v13].vData.lVal = *((_DWORD *)this + 16);
        }
        else
        {
          VariantInit(p_vData);
        }
        ++v12;
        ++v13;
      }
      while ( v12 < a2 );
    }
    return 0;
  }
  v10 = -2147024882;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147024882, L"<CDataConvert::GetInfo|OLEDB|ERR> ", 0x236Du);
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 9287689;
      return (unsigned int)bidTraceHR(off_1800C8390[0], v11, L"<CDataConvert::GetInfo|Trace|HR> ", v10);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18003f2d0  push    rbx
0x18003f2d2  push    rbp
0x18003f2d3  push    rsi
0x18003f2d4  push    rdi
0x18003f2d5  push    r14
0x18003f2d7  push    r15
0x18003f2d9  sub     rsp, 28h
0x18003f2dd  mov     esi, edx
0x18003f2df  mov     rbx, r9
0x18003f2e2  mov     r14, r8
0x18003f2e5  mov     r15, rcx
0x18003f2e8  test    edx, edx
0x18003f2ea  jz      loc_18003F3AB
0x18003f2f0  test    r8, r8
0x18003f2f3  jz      loc_18003F3AB
0x18003f2f9  test    rbx, rbx
0x18003f2fc  jnz     short loc_18003F305
0x18003f2fe  xor     eax, eax
0x18003f300  jmp     loc_18003F403
0x18003f305  mov     rcx, rsi
0x18003f308  shl     rcx, 5; cb
0x18003f30c  call    cs:__imp_CoTaskMemAlloc
0x18003f312  mov     [rbx], rax
0x18003f315  test    rax, rax
0x18003f318  jnz     short loc_18003F359
0x18003f31a  mov     eax, cs:_bidGblFlags
0x18003f320  mov     ebx, 8007000Eh
0x18003f325  test    al, 2
0x18003f327  jz      loc_18003F401
0x18003f32d  mov     r8d, 236Dh; unsigned int
0x18003f333  lea     rdx, aCdataconvertGe_0; "<CDataConvert::GetInfo|OLEDB|ERR> "
0x18003f33a  mov     ecx, ebx; int
0x18003f33c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003f341  mov     eax, cs:_bidGblFlags
0x18003f347  test    al, 2
0x18003f349  jz      loc_18003F401
0x18003f34f  mov     edx, 8DB809h
0x18003f354  jmp     loc_18003F3E9
0x18003f359  xor     ebp, ebp
0x18003f35b  test    esi, esi
0x18003f35d  jz      short loc_18003F2FE
0x18003f35f  xor     edi, edi
0x18003f361  mov     rcx, [rbx]
0x18003f364  mov     r8, rdi
0x18003f367  mov     eax, [r14+rdi*4]
0x18003f36b  shl     r8, 5
0x18003f36f  mov     [r8+rcx], eax
0x18003f373  mov     rcx, [rbx]
0x18003f376  add     rcx, 8
0x18003f37a  add     rcx, r8; pvarg
0x18003f37d  cmp     dword ptr [r14+rdi*4], 1
0x18003f382  jz      short loc_18003F38C
0x18003f384  call    cs:__imp_VariantInit
0x18003f38a  jmp     short loc_18003F39D
0x18003f38c  mov     word ptr [rcx], 13h
0x18003f391  mov     rcx, [rbx]
0x18003f394  mov     eax, [r15+40h]
0x18003f398  mov     [r8+rcx+10h], eax
0x18003f39d  inc     ebp
0x18003f39f  inc     rdi
0x18003f3a2  cmp     ebp, esi
0x18003f3a4  jb      short loc_18003F361
0x18003f3a6  jmp     loc_18003F2FE
0x18003f3ab  test    rbx, rbx
0x18003f3ae  jz      short loc_18003F3B7
0x18003f3b0  mov     qword ptr [r9], 0
0x18003f3b7  mov     eax, cs:_bidGblFlags
0x18003f3bd  mov     ebx, 80070057h
0x18003f3c2  test    al, 2
0x18003f3c4  jz      short loc_18003F401
0x18003f3c6  mov     r8d, 2363h; unsigned int
0x18003f3cc  lea     rdx, aCdataconvertGe_0; "<CDataConvert::GetInfo|OLEDB|ERR> "
0x18003f3d3  mov     ecx, ebx; int
0x18003f3d5  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003f3da  mov     eax, cs:_bidGblFlags
0x18003f3e0  test    al, 2
0x18003f3e2  jz      short loc_18003F401
0x18003f3e4  mov     edx, 8D9009h
0x18003f3e9  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18003f3f0  lea     r8, aCdataconvertGe; "<CDataConvert::GetInfo|Trace|HR> "
0x18003f3f7  mov     r9d, ebx
0x18003f3fa  call    _bidTraceHR
0x18003f3ff  mov     ebx, eax
0x18003f401  mov     eax, ebx
0x18003f403  add     rsp, 28h
0x18003f407  pop     r15
0x18003f409  pop     r14
0x18003f40b  pop     rdi
0x18003f40c  pop     rsi
0x18003f40d  pop     rbp
0x18003f40e  pop     rbx
0x18003f40f  retn
```
