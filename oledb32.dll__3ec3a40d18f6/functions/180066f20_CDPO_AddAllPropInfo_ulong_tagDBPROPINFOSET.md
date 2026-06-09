# CDPO::AddAllPropInfo(ulong *,tagDBPROPINFOSET * *)

- ea: `0x180066f20`
- end: `0x180067189`
- name: `?AddAllPropInfo@CDPO@@AEAAJPEAKPEAPEAUtagDBPROPINFOSET@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(CDPO *__hidden this, unsigned int *, struct tagDBPROPINFOSET **)`
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
- `0x180066f20`
- `0x18007e6ca`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800670a3`
- `OLEAUT32!__imp_VariantInit` at `0x1800670a3`
- `OLEAUT32!__imp_VariantCopy` at `0x1800670bb`
- `OLEAUT32!__imp_VariantCopy` at `0x1800670bb`
- `ole32!CoTaskMemAlloc` at `0x18006702c`
- `ole32!CoTaskMemAlloc` at `0x18006702c`
- `ole32!CoTaskMemRealloc` at `0x180066f67`
- `ole32!CoTaskMemRealloc` at `0x180066f67`

## pseudocode

```c
__int64 __fastcall CDPO::AddAllPropInfo(CDPO *this, unsigned int *a2, LPVOID *a3)
{
  __int64 v3; // r13
  unsigned int *v4; // r12
  __int64 v5; // rax
  LPVOID *v7; // r14
  __int64 v8; // rdi
  char *v9; // rax
  int v10; // ebx
  unsigned int v11; // esi
  __int64 v12; // rbp
  char *v13; // rbx
  __int64 v14; // r14
  __int64 v15; // r15
  void *v16; // rax
  unsigned int v17; // r13d
  char *v18; // r12
  __int64 v19; // rbx
  __int64 v20; // rdi
  int v21; // ebx
  unsigned int *pExceptionObject; // [rsp+88h] [rbp+10h] BYREF
  LPVOID *v24; // [rsp+90h] [rbp+18h]
  int v25; // [rsp+98h] [rbp+20h]

  v24 = a3;
  pExceptionObject = a2;
  v3 = *a2;
  v4 = a2;
  v5 = *((_QWORD *)this + 15);
  v7 = a3;
  v25 = v3;
  v8 = *(unsigned int *)(v5 + 1088);
  *a2 = v8 + v3;
  v9 = (char *)CoTaskMemRealloc(*a3, 32LL * (unsigned int)(v8 + v3));
  if ( !v9 )
  {
    v10 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<CDPO::AddAllPropInfo|OLEDB|ERR> ", 0x69u);
      if ( (bidGblFlags & 2) != 0 )
        v10 = bidTraceHR(off_1800C8450[0], 107529, L"<CDPO::AddAllPropInfo|Trace|HR> ", 2147942414LL);
    }
    LODWORD(pExceptionObject) = v10;
    throw (long *)&pExceptionObject;
  }
  *v7 = v9;
  memset_0(&v9[32 * v3], 0, 32 * v8);
  v11 = v3;
  v12 = *(_QWORD *)(*((_QWORD *)this + 15) + 1096LL);
  while ( v11 < *v4 )
  {
    v13 = (char *)*v7;
    v14 = 32LL * (v11 - (unsigned int)v3);
    v15 = 32LL * v11;
    v16 = CoTaskMemAlloc(48LL * *(unsigned int *)(v14 + v12 + 8));
    *(_QWORD *)&v13[v15] = v16;
    if ( !v16 )
    {
      v21 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024882, L"<CDPO::AddAllPropInfo|OLEDB|ERR> ", 0x75u);
        if ( (bidGblFlags & 2) != 0 )
          v21 = bidTraceHR(off_1800C8450[0], 119817, L"<CDPO::AddAllPropInfo|Trace|HR> ", 2147942414LL);
      }
      LODWORD(pExceptionObject) = v21;
      throw (long *)&pExceptionObject;
    }
    *(_OWORD *)&v13[v15 + 12] = *(_OWORD *)(v14 + v12 + 12);
    *(_DWORD *)&v13[v15 + 8] = *(_DWORD *)(v14 + v12 + 8);
    memcpy_0(v16, *(const void **)(v14 + v12), 48LL * *(unsigned int *)(v14 + v12 + 8));
    if ( *(_DWORD *)(v14 + v12 + 8) )
    {
      v17 = 0;
      v18 = v13;
      do
      {
        v19 = *(_QWORD *)&v18[v15];
        v20 = 48LL * v17;
        VariantInit((VARIANTARG *)(v19 + v20 + 24));
        VariantCopy((VARIANTARG *)(v19 + v20 + 24), (const VARIANTARG *)(v20 + *(_QWORD *)(v14 + v12) + 24LL));
        ++v17;
      }
      while ( v17 < *(_DWORD *)(v14 + v12 + 8) );
      v4 = pExceptionObject;
      LODWORD(v3) = v25;
    }
    v7 = v24;
    ++v11;
  }
  if ( (bidGblFlags & 2) != 0 )
    return bidTraceHR(off_1800C8450[0], 134153, L"<CDPO::AddAllPropInfo|Trace|HR> ", 0);
  else
    return 0;
}

```

## disassembly

```asm
0x180066f20  mov     [rsp+arg_10], r8
0x180066f25  mov     [rsp+pExceptionObject], rdx
0x180066f2a  push    rbx
0x180066f2b  push    rbp
0x180066f2c  push    rsi
0x180066f2d  push    rdi
0x180066f2e  push    r12
0x180066f30  push    r13
0x180066f32  push    r14
0x180066f34  push    r15
0x180066f36  sub     rsp, 38h
0x180066f3a  mov     r13d, [rdx]
0x180066f3d  mov     r12, rdx
0x180066f40  mov     rax, [rcx+78h]
0x180066f44  mov     rbx, rcx
0x180066f47  mov     r14, r8
0x180066f4a  mov     [rsp+78h+arg_18], r13d
0x180066f52  mov     edi, [rax+440h]
0x180066f58  lea     eax, [rdi+r13]
0x180066f5c  mov     [rdx], eax
0x180066f5e  mov     rcx, [r8]; pv
0x180066f61  mov     edx, eax
0x180066f63  shl     rdx, 5; cb
0x180066f67  call    cs:__imp_CoTaskMemRealloc
0x180066f6d  test    rax, rax
0x180066f70  jnz     short loc_180066FD8
0x180066f72  mov     eax, cs:_bidGblFlags
0x180066f78  mov     ebx, 8007000Eh
0x180066f7d  test    al, 2
0x180066f7f  jz      short loc_180066FBC
0x180066f81  mov     r8d, 69h ; 'i'; unsigned int
0x180066f87  lea     rdx, aCdpoAddallprop; "<CDPO::AddAllPropInfo|OLEDB|ERR> "
0x180066f8e  mov     ecx, ebx; int
0x180066f90  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180066f95  mov     eax, cs:_bidGblFlags
0x180066f9b  test    al, 2
0x180066f9d  jz      short loc_180066FBC
0x180066f9f  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180066fa6  lea     r8, aCdpoAddallprop_0; "<CDPO::AddAllPropInfo|Trace|HR> "
0x180066fad  mov     r9d, ebx
0x180066fb0  mov     edx, 1A409h
0x180066fb5  call    _bidTraceHR
0x180066fba  mov     ebx, eax
0x180066fbc  lea     rdx, _TI1J; pThrowInfo
0x180066fc3  mov     dword ptr [rsp+78h+pExceptionObject], ebx
0x180066fca  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180066fd2  call    _CxxThrowException_0
0x180066fd8  mov     rcx, r13
0x180066fdb  mov     [r14], rax
0x180066fde  shl     rcx, 5
0x180066fe2  mov     r8, rdi
0x180066fe5  add     rcx, rax; void *
0x180066fe8  shl     r8, 5; Size
0x180066fec  xor     edx, edx; Val
0x180066fee  call    memset_0
0x180066ff3  mov     rax, [rbx+78h]
0x180066ff7  mov     esi, r13d
0x180066ffa  mov     rbp, [rax+448h]
0x180067001  cmp     esi, [r12]
0x180067005  jnb     loc_180067150
0x18006700b  mov     rbx, [r14]
0x18006700e  mov     r14d, esi
0x180067011  sub     r14d, r13d
0x180067014  mov     r15d, esi
0x180067017  shl     r14, 5
0x18006701b  shl     r15, 5
0x18006701f  mov     eax, [r14+rbp+8]
0x180067024  lea     rcx, [rax+rax*2]
0x180067028  shl     rcx, 4; cb
0x18006702c  call    cs:__imp_CoTaskMemAlloc
0x180067032  mov     [r15+rbx], rax
0x180067036  test    rax, rax
0x180067039  jz      loc_1800670EA
0x18006703f  movups  xmm0, xmmword ptr [r14+rbp+0Ch]
0x180067045  movdqu  xmmword ptr [r15+rbx+0Ch], xmm0
0x18006704c  mov     ecx, [r14+rbp+8]
0x180067051  mov     [r15+rbx+8], ecx
0x180067056  mov     ecx, [r14+rbp+8]
0x18006705b  mov     rdx, [r14+rbp]; Src
0x18006705f  lea     r8, [rcx+rcx*2]
0x180067063  mov     rcx, rax; void *
0x180067066  shl     r8, 4; Size
0x18006706a  call    memcpy_0
0x18006706f  cmp     dword ptr [r14+rbp+8], 0
0x180067075  mov     [rsp+78h+arg_0], 0
0x180067080  jbe     short loc_1800670DB
0x180067082  mov     r13d, [rsp+78h+arg_0]
0x18006708a  mov     r12, rbx
0x18006708d  mov     rbx, [r15+r12]
0x180067091  mov     eax, r13d
0x180067094  lea     rdi, [rax+rax*2]
0x180067098  shl     rdi, 4
0x18006709c  lea     rcx, [rdi+18h]
0x1800670a0  add     rcx, rbx; pvarg
0x1800670a3  call    cs:__imp_VariantInit
0x1800670a9  mov     rdx, [r14+rbp]
0x1800670ad  lea     rcx, [rdi+18h]
0x1800670b1  add     rdx, 18h
0x1800670b5  add     rcx, rbx; pvargDest
0x1800670b8  add     rdx, rdi; pvargSrc
0x1800670bb  call    cs:__imp_VariantCopy
0x1800670c1  inc     r13d
0x1800670c4  cmp     r13d, [r14+rbp+8]
0x1800670c9  jb      short loc_18006708D
0x1800670cb  mov     r12, [rsp+78h+pExceptionObject]
0x1800670d3  mov     r13d, [rsp+78h+arg_18]
0x1800670db  mov     r14, [rsp+78h+arg_10]
0x1800670e3  inc     esi
0x1800670e5  jmp     loc_180067001
0x1800670ea  mov     eax, cs:_bidGblFlags
0x1800670f0  mov     ebx, 8007000Eh
0x1800670f5  test    al, 2
0x1800670f7  jz      short loc_180067134
0x1800670f9  mov     r8d, 75h ; 'u'; unsigned int
0x1800670ff  lea     rdx, aCdpoAddallprop; "<CDPO::AddAllPropInfo|OLEDB|ERR> "
0x180067106  mov     ecx, ebx; int
0x180067108  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006710d  mov     eax, cs:_bidGblFlags
0x180067113  test    al, 2
0x180067115  jz      short loc_180067134
0x180067117  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006711e  lea     r8, aCdpoAddallprop_0; "<CDPO::AddAllPropInfo|Trace|HR> "
0x180067125  mov     r9d, ebx
0x180067128  mov     edx, 1D409h
0x18006712d  call    _bidTraceHR
0x180067132  mov     ebx, eax
0x180067134  lea     rdx, _TI1J; pThrowInfo
0x18006713b  mov     dword ptr [rsp+78h+pExceptionObject], ebx
0x180067142  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18006714a  call    _CxxThrowException_0
0x180067150  test    byte ptr cs:_bidGblFlags, 2
0x180067157  jz      short loc_180067176
0x180067159  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180067160  lea     r8, aCdpoAddallprop_0; "<CDPO::AddAllPropInfo|Trace|HR> "
0x180067167  xor     r9d, r9d
0x18006716a  mov     edx, 20C09h
0x18006716f  call    _bidTraceHR
0x180067174  jmp     short loc_180067178
0x180067176  xor     eax, eax
0x180067178  add     rsp, 38h
0x18006717c  pop     r15
0x18006717e  pop     r14
0x180067180  pop     r13
0x180067182  pop     r12
0x180067184  pop     rdi
0x180067185  pop     rsi
0x180067186  pop     rbp
0x180067187  pop     rbx
0x180067188  retn
```
