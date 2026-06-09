# FixupFromWstr(ushort *,ulong,ushort,void *,unsigned __int64 *,unsigned __int64,ulong *,int)

- ea: `0x180025314`
- end: `0x180025635`
- name: `?FixupFromWstr@@YAJPEAGKGPEAXPEA_K_KPEAKH@Z`
- size: `801`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned __int16@<r8w>, void *@<r9>, unsigned __int64 *, unsigned __int64, unsigned int *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180003320`

## callees

- `0x180013870`
- `0x180025314`
- `0x180029560`
- `0x18002ec26`
- `0x18003ef1c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800255b1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800255b1`
- `ole32!CoTaskMemAlloc` at `0x180025380`
- `ole32!CoTaskMemAlloc` at `0x18002549a`
- `ole32!CoTaskMemAlloc` at `0x180025380`
- `ole32!CoTaskMemAlloc` at `0x18002549a`
- `ole32!CoTaskMemFree` at `0x1800253fd`
- `ole32!CoTaskMemFree` at `0x1800253fd`

## pseudocode

```c
__int64 __fastcall FixupFromWstr(
        unsigned __int16 *a1,
        unsigned int a2,
        __int16 a3,
        unsigned __int8 *a4,
        unsigned __int64 *a5,
        unsigned __int64 a6,
        unsigned int *a7,
        int a8)
{
  unsigned int v10; // edi
  size_t *v12; // r12
  __int64 v13; // r14
  int v14; // ebp
  unsigned __int64 v15; // rsi
  unsigned __int8 *v16; // rax
  unsigned int v17; // r8d
  bool v18; // zf
  unsigned int v19; // eax
  unsigned int v20; // edx
  unsigned int v21; // ecx
  unsigned __int64 *v22; // r12
  int v23; // r14d
  unsigned __int64 v24; // rsi
  unsigned __int8 *v25; // rax
  unsigned int v26; // eax
  BSTR v28; // rax
  unsigned int v29; // ebx
  const char *v30; // [rsp+30h] [rbp-38h]
  const char *v31; // [rsp+30h] [rbp-38h]
  int v32; // [rsp+80h] [rbp+18h] BYREF

  v10 = 0;
  v32 = 0;
  if ( a3 != 8 )
  {
    if ( a3 == 129 )
    {
      v19 = FastWideCharToMultiByte((unsigned int)a1, a2, a1, a2, 0, 0, v30, 0);
      v22 = a5;
      v23 = a8;
      *a5 = v19;
      if ( v23 )
      {
        v24 = v19 + 1LL;
        v25 = (unsigned __int8 *)CoTaskMemAlloc(v24);
        *(_QWORD *)a4 = v25;
        if ( !v25 )
        {
          if ( (bidGblFlags & 2) != 0 )
            v10 = bidTraceHR(off_1800C8390[0], 9826313, L"<FixupFromWstr|Trace|HR> ", 2147942414LL);
          else
            v10 = -2147024882;
          if ( (bidGblFlags & 2) == 0 )
            return v10;
          v17 = 9597;
LABEL_11:
          OLEDBTraceErr(-2147024882, L"<FixupFromWstr|OLEDB|ERR> ", v17);
          goto LABEL_38;
        }
        a4 = v25;
      }
      else
      {
        v24 = a6;
      }
      if ( v24 )
      {
        v26 = FastWideCharToMultiByte(v21, v20, a1, a2, a4, v24, v31, &v32);
        if ( v26 == *v22 && v24 > v26 )
        {
          a4[v26] = 0;
          if ( v32 )
            *a7 = 4;
        }
        else
        {
          *a7 = 4;
          a4[v24 - 1] = 0;
        }
        goto LABEL_38;
      }
      v18 = v23 == 0;
    }
    else
    {
      if ( a3 != 130 )
        goto LABEL_38;
      v12 = a5;
      v13 = 2LL * a2;
      v14 = a8;
      *a5 = v13;
      if ( v14 )
      {
        v15 = v13 + 2;
        v16 = (unsigned __int8 *)CoTaskMemAlloc(v13 + 2);
        *(_QWORD *)a4 = v16;
        if ( !v16 )
        {
          if ( (bidGblFlags & 2) != 0 )
            v10 = bidTraceHR(off_1800C8390[0], 9749513, L"<FixupFromWstr|Trace|HR> ", 2147942414LL);
          else
            v10 = -2147024882;
          if ( (bidGblFlags & 2) == 0 )
            return v10;
          v17 = 9522;
          goto LABEL_11;
        }
        a4 = v16;
      }
      else
      {
        v15 = a6;
      }
      if ( v15 >= 2 )
      {
        if ( *v12 + 2 > v15 )
        {
          *a7 = 4;
          memcpy_0(a4, a1, v15 - 2);
          *(_WORD *)&a4[2 * (v15 >> 1) - 2] = 0;
        }
        else
        {
          memcpy_0(a4, a1, *v12);
          *(_WORD *)&a4[v13] = 0;
        }
LABEL_38:
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v10, L"<FixupFromWstr|OLEDB|ERR> ", 0x25B6u);
          if ( (bidGblFlags & 2) != 0 )
            return (unsigned int)bidTraceHR(off_1800C8390[0], 9886729, L"<FixupFromWstr|Trace|HR> ", v10);
        }
        return v10;
      }
      v18 = v14 == 0;
    }
    if ( !v18 )
      CoTaskMemFree(a4);
    *a7 = 6;
    goto LABEL_38;
  }
  v28 = SysAllocStringLen(a1, a2);
  *(_QWORD *)a4 = v28;
  if ( v28 )
  {
    *a5 = 8;
    return 0;
  }
  else
  {
    v29 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<FixupFromWstr|OLEDB|ERR> ", 0x250Bu);
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(off_1800C8390[0], 9711625, L"<FixupFromWstr|Trace|HR> ", 2147942414LL);
    }
    return v29;
  }
}

```

## disassembly

```asm
0x180025314  mov     rax, rsp
0x180025317  mov     [rax+8], rbx
0x18002531b  mov     [rax+10h], rbp
0x18002531f  push    rsi
0x180025320  push    rdi
0x180025321  push    r12
0x180025323  push    r14
0x180025325  push    r15
0x180025327  sub     rsp, 40h
0x18002532b  mov     rbx, r9
0x18002532e  mov     ebp, edx
0x180025330  xor     edi, edi
0x180025332  movzx   r9d, r8w
0x180025336  mov     [rax+18h], edi
0x180025339  mov     r15, rcx
0x18002533c  sub     r9d, 8
0x180025340  jz      loc_1800255AF
0x180025346  sub     r9d, 79h ; 'y'
0x18002534a  jz      loc_180025460
0x180025350  cmp     r9d, 1
0x180025354  jnz     loc_180025568
0x18002535a  mov     r12, [rsp+68h+arg_20]
0x180025362  lea     r14, ds:0[rbp*2]
0x18002536a  mov     ebp, [rsp+68h+arg_38]
0x180025371  mov     [r12], r14
0x180025375  test    ebp, ebp
0x180025377  jz      short loc_1800253E8
0x180025379  lea     rsi, [r14+2]
0x18002537d  mov     rcx, rsi; cb
0x180025380  call    cs:__imp_CoTaskMemAlloc
0x180025386  mov     [rbx], rax
0x180025389  test    rax, rax
0x18002538c  jnz     short loc_1800253E3
0x18002538e  test    byte ptr cs:_bidGblFlags, 2
0x180025395  mov     ebx, 8007000Eh
0x18002539a  jz      short loc_1800253BB
0x18002539c  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800253a3  lea     r8, aFixupfromwstrT; "<FixupFromWstr|Trace|HR> "
0x1800253aa  mov     r9d, ebx
0x1800253ad  mov     edx, 94C409h
0x1800253b2  call    _bidTraceHR
0x1800253b7  mov     edi, eax
0x1800253b9  jmp     short loc_1800253BD
0x1800253bb  mov     edi, ebx
0x1800253bd  test    byte ptr cs:_bidGblFlags, 2
0x1800253c4  jz      loc_1800255AB
0x1800253ca  mov     r8d, 2532h; unsigned int
0x1800253d0  lea     rdx, aFixupfromwstrO; "<FixupFromWstr|OLEDB|ERR> "
0x1800253d7  mov     ecx, ebx; int
0x1800253d9  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800253de  jmp     loc_180025568
0x1800253e3  mov     rbx, rax
0x1800253e6  jmp     short loc_1800253F0
0x1800253e8  mov     rsi, [rsp+68h+arg_28]
0x1800253f0  cmp     rsi, 2
0x1800253f4  jnb     short loc_180025416
0x1800253f6  test    ebp, ebp
0x1800253f8  jz      short loc_180025403
0x1800253fa  mov     rcx, rbx; pv
0x1800253fd  call    cs:__imp_CoTaskMemFree
0x180025403  mov     rax, [rsp+68h+arg_30]
0x18002540b  mov     dword ptr [rax], 6
0x180025411  jmp     loc_180025568
0x180025416  mov     r8, [r12]; Size
0x18002541a  mov     rdx, r15; Src
0x18002541d  mov     rcx, rbx; void *
0x180025420  lea     rax, [r8+2]
0x180025424  cmp     rax, rsi
0x180025427  ja      short loc_18002543A
0x180025429  call    memcpy_0
0x18002542e  xor     eax, eax
0x180025430  mov     [r14+rbx], ax
0x180025435  jmp     loc_180025568
0x18002543a  mov     rax, [rsp+68h+arg_30]
0x180025442  lea     r8, [rsi-2]; Size
0x180025446  mov     dword ptr [rax], 4
0x18002544c  call    memcpy_0
0x180025451  shr     rsi, 1
0x180025454  xor     eax, eax
0x180025456  mov     [rbx+rsi*2-2], ax
0x18002545b  jmp     loc_180025568
0x180025460  mov     [rsp+68h+var_30], rdi; int *
0x180025465  mov     r9d, ebp; int
0x180025468  mov     [rsp+68h+var_40], edi; int
0x18002546c  mov     r8, r15; unsigned __int16 *
0x18002546f  mov     [rsp+68h+var_48], rdi; unsigned __int8 *
0x180025474  call    ?FastWideCharToMultiByte@@YAHIKPEBGHPEAEHPEBDPEAH@Z; FastWideCharToMultiByte(uint,ulong,ushort const *,int,uchar *,int,char const *,int *)
0x180025479  mov     r12, [rsp+68h+arg_20]
0x180025481  mov     r14d, [rsp+68h+arg_38]
0x180025489  mov     esi, eax
0x18002548b  mov     [r12], rsi
0x18002548f  test    r14d, r14d
0x180025492  jz      short loc_1800254F4
0x180025494  inc     rsi
0x180025497  mov     rcx, rsi; cb
0x18002549a  call    cs:__imp_CoTaskMemAlloc
0x1800254a0  mov     [rbx], rax
0x1800254a3  test    rax, rax
0x1800254a6  jnz     short loc_1800254EF
0x1800254a8  test    byte ptr cs:_bidGblFlags, 2
0x1800254af  mov     ebx, 8007000Eh
0x1800254b4  jz      short loc_1800254D5
0x1800254b6  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800254bd  lea     r8, aFixupfromwstrT; "<FixupFromWstr|Trace|HR> "
0x1800254c4  mov     r9d, ebx
0x1800254c7  mov     edx, 95F009h
0x1800254cc  call    _bidTraceHR
0x1800254d1  mov     edi, eax
0x1800254d3  jmp     short loc_1800254D7
0x1800254d5  mov     edi, ebx
0x1800254d7  test    byte ptr cs:_bidGblFlags, 2
0x1800254de  jz      loc_1800255AB
0x1800254e4  mov     r8d, 257Dh
0x1800254ea  jmp     loc_1800253D0
0x1800254ef  mov     rbx, rax
0x1800254f2  jmp     short loc_1800254FC
0x1800254f4  mov     rsi, [rsp+68h+arg_28]
0x1800254fc  cmp     rsi, 1
0x180025500  jnb     short loc_18002550A
0x180025502  test    r14d, r14d
0x180025505  jmp     loc_1800253F8
0x18002550a  lea     rax, [rsp+68h+arg_10]
0x180025512  mov     r9d, ebp; int
0x180025515  mov     [rsp+68h+var_30], rax; int *
0x18002551a  mov     r8, r15; unsigned __int16 *
0x18002551d  mov     [rsp+68h+var_40], esi; int
0x180025521  mov     [rsp+68h+var_48], rbx; unsigned __int8 *
0x180025526  call    ?FastWideCharToMultiByte@@YAHIKPEBGHPEAEHPEBDPEAH@Z; FastWideCharToMultiByte(uint,ulong,ushort const *,int,uchar *,int,char const *,int *)
0x18002552b  mov     eax, eax
0x18002552d  cmp     rax, [r12]
0x180025531  jnz     short loc_180025555
0x180025533  cmp     rsi, rax
0x180025536  jbe     short loc_180025555
0x180025538  mov     [rax+rbx], dil
0x18002553c  cmp     [rsp+68h+arg_10], edi
0x180025543  jz      short loc_180025568
0x180025545  mov     rax, [rsp+68h+arg_30]
0x18002554d  mov     dword ptr [rax], 4
0x180025553  jmp     short loc_180025568
0x180025555  mov     rax, [rsp+68h+arg_30]
0x18002555d  mov     dword ptr [rax], 4
0x180025563  mov     [rbx+rsi-1], dil
0x180025568  test    byte ptr cs:_bidGblFlags, 2
0x18002556f  jz      short loc_1800255AB
0x180025571  mov     r8d, 25B6h; unsigned int
0x180025577  lea     rdx, aFixupfromwstrO; "<FixupFromWstr|OLEDB|ERR> "
0x18002557e  mov     ecx, edi; int
0x180025580  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180025585  test    byte ptr cs:_bidGblFlags, 2
0x18002558c  jz      short loc_1800255AB
0x18002558e  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180025595  lea     r8, aFixupfromwstrT; "<FixupFromWstr|Trace|HR> "
0x18002559c  mov     r9d, edi
0x18002559f  mov     edx, 96DC09h
0x1800255a4  call    _bidTraceHR
0x1800255a9  mov     edi, eax
0x1800255ab  mov     eax, edi
0x1800255ad  jmp     short loc_18002561E
0x1800255af  mov     edx, ebp; ui
0x1800255b1  call    cs:__imp_SysAllocStringLen
0x1800255b7  mov     [rbx], rax
0x1800255ba  test    rax, rax
0x1800255bd  jnz     short loc_18002560D
0x1800255bf  mov     eax, cs:_bidGblFlags
0x1800255c5  mov     ebx, 8007000Eh
0x1800255ca  test    al, 2
0x1800255cc  jz      short loc_180025609
0x1800255ce  mov     r8d, 250Bh; unsigned int
0x1800255d4  lea     rdx, aFixupfromwstrO; "<FixupFromWstr|OLEDB|ERR> "
0x1800255db  mov     ecx, ebx; int
0x1800255dd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800255e2  mov     eax, cs:_bidGblFlags
0x1800255e8  test    al, 2
0x1800255ea  jz      short loc_180025609
0x1800255ec  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800255f3  lea     r8, aFixupfromwstrT; "<FixupFromWstr|Trace|HR> "
0x1800255fa  mov     r9d, ebx
0x1800255fd  mov     edx, 943009h
0x180025602  call    _bidTraceHR
0x180025607  mov     ebx, eax
0x180025609  mov     eax, ebx
0x18002560b  jmp     short loc_18002561E
0x18002560d  mov     rax, [rsp+68h+arg_20]
0x180025615  mov     qword ptr [rax], 8
0x18002561c  xor     eax, eax
0x18002561e  mov     rbx, [rsp+68h+arg_0]
0x180025623  mov     rbp, [rsp+68h+arg_8]
0x180025628  add     rsp, 40h
0x18002562c  pop     r15
0x18002562e  pop     r14
0x180025630  pop     r12
0x180025632  pop     rdi
0x180025633  pop     rsi
0x180025634  retn
```
