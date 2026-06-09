# CConnection::getKeywords(long *,ushort * * *)

- ea: `0x180075050`
- end: `0x18007554b`
- name: `?getKeywords@CConnection@@QEAAJPEAJPEAPEAPEAG@Z`
- size: `1275`
- prototype: `__int64 __fastcall(CConnection *__hidden this, int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180070c10`

## callees

- `0x1800474ac`
- `0x18006a22c`
- `0x1800747cc`
- `0x180075050`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `msvcrt!wcschr` at `0x180075214`
- `msvcrt!wcschr` at `0x1800752bf`
- `msvcrt!wcschr` at `0x180075214`
- `msvcrt!wcschr` at `0x1800752bf`
- `MSDART!MpHeapAlloc` at `0x180075238`
- `MSDART!MpHeapAlloc` at `0x1800752ff`
- `MSDART!MpHeapAlloc` at `0x180075361`
- `MSDART!MpHeapAlloc` at `0x180075238`
- `MSDART!MpHeapAlloc` at `0x1800752ff`
- `MSDART!MpHeapAlloc` at `0x180075361`
- `ole32!CoTaskMemFree` at `0x18007550e`
- `ole32!CoTaskMemFree` at `0x18007550e`

## pseudocode

```c
__int64 __fastcall CConnection::getKeywords(CConnection *this, int *a2, unsigned __int16 ***a3)
{
  int v3; // ebp
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  int v8; // ebx
  __int64 BidObjectID; // r9
  __int64 v10; // r9
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  wchar_t *v16; // rax
  unsigned __int16 **v17; // rax
  bool v18; // zf
  __int64 v19; // r9
  wchar_t *v20; // r14
  wchar_t *v21; // rax
  wchar_t *v22; // r15
  __int64 v23; // r13
  unsigned __int16 *v24; // rax
  int v25; // eax
  __int64 v26; // rax
  unsigned __int64 v27; // r15
  unsigned __int16 *v28; // rax
  __int64 v29; // r9
  __int64 v30; // r9
  __int64 v31; // r9
  __int64 v32; // r9
  int v34; // [rsp+20h] [rbp-48h]
  int v35; // [rsp+28h] [rbp-40h]
  wchar_t *Str; // [rsp+70h] [rbp+8h] BYREF
  __int64 v37; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int64 v38; // [rsp+80h] [rbp+18h]

  v3 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 121);
  v37 = 0;
  Str = 0;
  *a2 = 0;
  *a3 = 0;
  if ( !v5 )
  {
    v8 = -2146824579;
    if ( (bidGblFlags & 2) == 0 )
      return (unsigned int)v8;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      bidTraceW(off_18012A1C0[0], 2905097, L"<CConnection::getKeywords|ADO|ERR> %u#, line %d\n", BidObjectID, 2837);
      goto LABEL_57;
    }
    v10 = 2837;
    v11 = 2905097;
LABEL_56:
    bidTraceW(off_18012A1C0[0], v11, L"<CConnection::getKeywords|ADO|ERR>  line %d\n", v10);
    goto LABEL_57;
  }
  v8 = (**v5)(v5, &IID_IDBInfo, &v37);
  if ( v8 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_57;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v13 = 2907145;
      v35 = 2839;
LABEL_10:
      bidTraceW(
        off_18012A1C0[0],
        v13,
        L"<CConnection::getKeywords|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v12,
        v8,
        v35);
      goto LABEL_57;
    }
    v34 = 2839;
    v14 = 2907145;
    goto LABEL_12;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v37 + 24LL))(v37, &Str);
  if ( v8 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_57;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v13 = 2910217;
      v35 = 2842;
      goto LABEL_10;
    }
    v34 = 2842;
    v14 = 2910217;
LABEL_12:
    bidTraceW(
      off_18012A1C0[0],
      v14,
      L"<CConnection::getKeywords|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)v8,
      v34);
    goto LABEL_57;
  }
  v15 = Str;
  if ( !Str || !*Str )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_57;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      v32 = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      bidTraceW(off_18012A1C0[0], 2913289, L"<CConnection::getKeywords|ADO|ERR> %u#, line %d\n", v32, 2845);
      goto LABEL_57;
    }
    v10 = 2845;
    v11 = 2913289;
    goto LABEL_56;
  }
  *a2 = 1;
  while ( 1 )
  {
    v16 = wcschr(v15, 0x2Cu);
    if ( !v16 )
      break;
    ++*a2;
    v15 = v16 + 1;
  }
  v17 = (unsigned __int16 **)MpHeapAlloc(g_hHeapHandle, 10485760, 8LL * *a2);
  *a3 = v17;
  if ( v17 )
  {
    v20 = Str;
    while ( v3 < *a2 )
    {
      v21 = wcschr(v20, 0x2Cu);
      v22 = v21;
      if ( v21 )
      {
        v23 = v21 - v20;
        v38 = (int)v23 + 1;
        v24 = (unsigned __int16 *)MpHeapAlloc(g_hHeapHandle, 10485760, 2 * v38);
        (*a3)[v3] = v24;
        if ( !v24 )
        {
          v18 = (bidGblFlags & 2) == 0;
          v8 = -2147024882;
          *a2 = v3;
          if ( v18 )
            goto LABEL_57;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            v30 = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            bidTraceW(off_18012A1C0[0], 2951177, L"<CConnection::getKeywords|ADO|ERR> %u#, line %d\n", v30, 2882);
            goto LABEL_57;
          }
          v10 = 2882;
          v11 = 2951177;
          goto LABEL_56;
        }
        v25 = StringCchCopyNW(v24, v38, v20, (int)v23);
        if ( v25 < 0 )
        {
          v18 = (bidGblFlags & 2) == 0;
          v8 = v25;
          *a2 = v3;
          if ( v18 )
            goto LABEL_57;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            v29 = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            bidTraceW(off_18012A1C0[0], 2961417, L"<CConnection::getKeywords|ADO|ERR> %u#, line %d\n", v29, 2892);
            goto LABEL_57;
          }
          v10 = 2892;
          v11 = 2961417;
          goto LABEL_56;
        }
        v20 = v22 + 1;
      }
      else
      {
        v26 = -1;
        do
          ++v26;
        while ( v20[v26] );
        v27 = v26 + 1;
        v28 = (unsigned __int16 *)MpHeapAlloc(g_hHeapHandle, 10485760, 2 * (v26 + 1));
        (*a3)[v3] = v28;
        if ( !v28 )
        {
          v18 = (bidGblFlags & 2) == 0;
          v8 = -2147024882;
          *a2 = v3;
          if ( v18 )
            goto LABEL_57;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            v31 = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            bidTraceW(off_18012A1C0[0], 2975753, L"<CConnection::getKeywords|ADO|ERR> %u#, line %d\n", v31, 2906);
            goto LABEL_57;
          }
          v10 = 2906;
          v11 = 2975753;
          goto LABEL_56;
        }
        StringCchCopyW(v28, v27, v20);
      }
      ++v3;
    }
    goto LABEL_57;
  }
  v18 = (bidGblFlags & 2) == 0;
  v8 = -2147024882;
  *a2 = 0;
  if ( !v18 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      v19 = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      bidTraceW(off_18012A1C0[0], 2930697, L"<CConnection::getKeywords|ADO|ERR> %u#, line %d\n", v19, 2862);
      goto LABEL_57;
    }
    v10 = 2862;
    v11 = 2930697;
    goto LABEL_56;
  }
LABEL_57:
  if ( Str )
    CoTaskMemFree(Str);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180075050  mov     [rsp+arg_18], rbx
0x180075055  push    rbp
0x180075056  push    rsi
0x180075057  push    rdi
0x180075058  push    r12
0x18007505a  push    r13
0x18007505c  push    r14
0x18007505e  push    r15
0x180075060  sub     rsp, 30h
0x180075064  xor     ebp, ebp
0x180075066  mov     rsi, rcx
0x180075069  mov     rcx, [rcx+3C8h]
0x180075070  mov     r12, r8
0x180075073  mov     [rsp+68h+arg_8], rbp
0x180075078  mov     rdi, rdx
0x18007507b  mov     [rsp+68h+Str], rbp
0x180075080  mov     [rdx], ebp
0x180075082  mov     [r8], rbp
0x180075085  test    rcx, rcx
0x180075088  jnz     short loc_1800750E5
0x18007508a  test    byte ptr cs:_bidGblFlags, 2
0x180075091  mov     ebx, 800A0E7Dh
0x180075096  jz      loc_180075530
0x18007509c  lea     rcx, [rsi+100h]; this
0x1800750a3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800750a8  cmp     eax, 0FFFFFFFFh
0x1800750ab  jz      short loc_1800750D5
0x1800750ad  lea     rcx, [rsi+100h]; this
0x1800750b4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800750b9  mov     r9d, eax
0x1800750bc  mov     [rsp+68h+var_48], 0B15h
0x1800750c4  lea     r8, aCconnectionGet_22; "<CConnection::getKeywords|ADO|ERR> %u#,"...
0x1800750cb  mov     edx, 2C5409h
0x1800750d0  jmp     loc_18007516F
0x1800750d5  mov     r9d, 0B15h
0x1800750db  mov     edx, 2C5409h
0x1800750e0  jmp     loc_1800754F1
0x1800750e5  mov     rax, [rcx]
0x1800750e8  lea     r8, [rsp+68h+arg_8]
0x1800750ed  lea     rdx, IID_IDBInfo
0x1800750f4  mov     rax, [rax]
0x1800750f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800750fc  mov     ebx, eax
0x1800750fe  test    eax, eax
0x180075100  jns     short loc_180075180
0x180075102  test    byte ptr cs:_bidGblFlags, 2
0x180075109  jz      loc_180075504
0x18007510f  lea     rcx, [rsi+100h]; this
0x180075116  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007511b  cmp     eax, 0FFFFFFFFh
0x18007511e  jz      short loc_180075158
0x180075120  lea     rcx, [rsi+100h]; this
0x180075127  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007512c  mov     edx, 2C5C09h
0x180075131  mov     [rsp+68h+var_40], 0B17h
0x180075139  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180075140  lea     r8, aCconnectionGet_12; "<CConnection::getKeywords|ADO|ERR> %u#,"...
0x180075147  mov     r9d, eax
0x18007514a  mov     [rsp+68h+var_48], ebx
0x18007514e  call    _bidTraceW
0x180075153  jmp     loc_180075504
0x180075158  mov     [rsp+68h+var_48], 0B17h
0x180075160  mov     edx, 2C5C09h
0x180075165  lea     r8, aCconnectionGet_4; "<CConnection::getKeywords|ADO|ERR> 0x%0"...
0x18007516c  mov     r9d, ebx
0x18007516f  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180075176  call    _bidTraceW
0x18007517b  jmp     loc_180075504
0x180075180  mov     rcx, [rsp+68h+arg_8]
0x180075185  lea     rdx, [rsp+68h+Str]
0x18007518a  mov     rax, [rcx]
0x18007518d  mov     rax, [rax+18h]
0x180075191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075196  mov     ebx, eax
0x180075198  test    eax, eax
0x18007519a  jns     short loc_1800751EA
0x18007519c  test    byte ptr cs:_bidGblFlags, 2
0x1800751a3  jz      loc_180075504
0x1800751a9  lea     rcx, [rsi+100h]; this
0x1800751b0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800751b5  cmp     eax, 0FFFFFFFFh
0x1800751b8  jz      short loc_1800751D8
0x1800751ba  lea     rcx, [rsi+100h]; this
0x1800751c1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800751c6  mov     edx, 2C6809h
0x1800751cb  mov     [rsp+68h+var_40], 0B1Ah
0x1800751d3  jmp     loc_180075139
0x1800751d8  mov     [rsp+68h+var_48], 0B1Ah
0x1800751e0  mov     edx, 2C6809h
0x1800751e5  jmp     loc_180075165
0x1800751ea  mov     rcx, [rsp+68h+Str]
0x1800751ef  test    rcx, rcx
0x1800751f2  jz      loc_1800754A4
0x1800751f8  cmp     [rcx], bp
0x1800751fb  jz      loc_1800754A4
0x180075201  mov     dword ptr [rdi], 1
0x180075207  jmp     short loc_18007520F
0x180075209  inc     dword ptr [rdi]
0x18007520b  lea     rcx, [rax+2]; Str
0x18007520f  mov     edx, 2Ch ; ','; Ch
0x180075214  call    cs:__imp_wcschr
0x18007521b  nop     dword ptr [rax+rax+00h]
0x180075220  test    rax, rax
0x180075223  jnz     short loc_180075209
0x180075225  movsxd  r8, dword ptr [rdi]
0x180075228  mov     edx, 0A00000h
0x18007522d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180075234  shl     r8, 3
0x180075238  call    cs:__imp_MpHeapAlloc
0x18007523f  nop     dword ptr [rax+rax+00h]
0x180075244  mov     [r12], rax
0x180075248  test    rax, rax
0x18007524b  jnz     short loc_1800752AA
0x18007524d  test    byte ptr cs:_bidGblFlags, 2
0x180075254  mov     ebx, 8007000Eh
0x180075259  mov     [rdi], ebp
0x18007525b  jz      loc_180075504
0x180075261  lea     rcx, [rsi+100h]; this
0x180075268  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007526d  cmp     eax, 0FFFFFFFFh
0x180075270  jz      short loc_18007529A
0x180075272  lea     rcx, [rsi+100h]; this
0x180075279  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007527e  mov     r9d, eax
0x180075281  mov     [rsp+68h+var_48], 0B2Eh
0x180075289  lea     r8, aCconnectionGet_22; "<CConnection::getKeywords|ADO|ERR> %u#,"...
0x180075290  mov     edx, 2CB809h
0x180075295  jmp     loc_18007516F
0x18007529a  mov     r9d, 0B2Eh
0x1800752a0  mov     edx, 2CB809h
0x1800752a5  jmp     loc_1800754F1
0x1800752aa  mov     r14, [rsp+68h+Str]
0x1800752af  cmp     ebp, [rdi]
0x1800752b1  jge     loc_180075504
0x1800752b7  mov     edx, 2Ch ; ','; Ch
0x1800752bc  mov     rcx, r14; Str
0x1800752bf  call    cs:__imp_wcschr
0x1800752c6  nop     dword ptr [rax+rax+00h]
0x1800752cb  xor     ecx, ecx
0x1800752cd  movsxd  r13, ebp
0x1800752d0  mov     r15, rax
0x1800752d3  test    rax, rax
0x1800752d6  jz      short loc_18007533F
0x1800752d8  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800752df  mov     r13, rax
0x1800752e2  sub     r13, r14
0x1800752e5  mov     edx, 0A00000h
0x1800752ea  sar     r13, 1
0x1800752ed  lea     eax, [r13+1]
0x1800752f1  cdqe
0x1800752f3  mov     [rsp+68h+arg_10], rax
0x1800752fb  lea     r8, [rax+rax]
0x1800752ff  call    cs:__imp_MpHeapAlloc
0x180075306  nop     dword ptr [rax+rax+00h]
0x18007530b  mov     rcx, [r12]
0x18007530f  movsxd  rdx, ebp
0x180075312  mov     [rcx+rdx*8], rax
0x180075316  test    rax, rax
0x180075319  jz      loc_1800753ED
0x18007531f  mov     rdx, [rsp+68h+arg_10]; unsigned __int64
0x180075327  mov     r8, r14; unsigned __int16 *
0x18007532a  movsxd  r9, r13d; unsigned __int64
0x18007532d  mov     rcx, rax; unsigned __int16 *
0x180075330  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180075335  test    eax, eax
0x180075337  js      short loc_180075393
0x180075339  lea     r14, [r15+2]
0x18007533d  jmp     short loc_18007538C
0x18007533f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180075343  inc     rax
0x180075346  cmp     [r14+rax*2], cx
0x18007534b  jnz     short loc_180075343
0x18007534d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180075354  lea     r15, [rax+1]
0x180075358  lea     r8, [r15+r15]
0x18007535c  mov     edx, 0A00000h
0x180075361  call    cs:__imp_MpHeapAlloc
0x180075368  nop     dword ptr [rax+rax+00h]
0x18007536d  mov     rcx, [r12]
0x180075371  mov     [rcx+r13*8], rax
0x180075375  test    rax, rax
0x180075378  jz      loc_18007544A
0x18007537e  mov     r8, r14; unsigned __int16 *
0x180075381  mov     rdx, r15; unsigned __int64
0x180075384  mov     rcx, rax; unsigned __int16 *
0x180075387  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007538c  inc     ebp
0x18007538e  jmp     loc_1800752AF
0x180075393  test    byte ptr cs:_bidGblFlags, 2
0x18007539a  mov     ebx, eax
0x18007539c  mov     [rdi], ebp
0x18007539e  jz      loc_180075504
0x1800753a4  lea     rcx, [rsi+100h]; this
0x1800753ab  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800753b0  cmp     eax, 0FFFFFFFFh
0x1800753b3  jz      short loc_1800753DD
0x1800753b5  lea     rcx, [rsi+100h]; this
0x1800753bc  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800753c1  mov     r9d, eax
0x1800753c4  mov     [rsp+68h+var_48], 0B4Ch
0x1800753cc  lea     r8, aCconnectionGet_22; "<CConnection::getKeywords|ADO|ERR> %u#,"...
0x1800753d3  mov     edx, 2D3009h
0x1800753d8  jmp     loc_18007516F
0x1800753dd  mov     r9d, 0B4Ch
0x1800753e3  mov     edx, 2D3009h
0x1800753e8  jmp     loc_1800754F1
0x1800753ed  test    byte ptr cs:_bidGblFlags, 2
0x1800753f4  mov     ebx, 8007000Eh
0x1800753f9  mov     [rdi], ebp
0x1800753fb  jz      loc_180075504
0x180075401  lea     rcx, [rsi+100h]; this
0x180075408  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007540d  cmp     eax, 0FFFFFFFFh
0x180075410  jz      short loc_18007543A
0x180075412  lea     rcx, [rsi+100h]; this
0x180075419  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007541e  mov     r9d, eax
0x180075421  mov     [rsp+68h+var_48], 0B42h
0x180075429  lea     r8, aCconnectionGet_22; "<CConnection::getKeywords|ADO|ERR> %u#,"...
0x180075430  mov     edx, 2D0809h
0x180075435  jmp     loc_18007516F
0x18007543a  mov     r9d, 0B42h
0x180075440  mov     edx, 2D0809h
0x180075445  jmp     loc_1800754F1
0x18007544a  test    byte ptr cs:_bidGblFlags, 2
0x180075451  mov     ebx, 8007000Eh
0x180075456  mov     [rdi], ebp
0x180075458  jz      loc_180075504
0x18007545e  lea     rcx, [rsi+100h]; this
0x180075465  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007546a  cmp     eax, 0FFFFFFFFh
0x18007546d  jz      short loc_180075497
0x18007546f  lea     rcx, [rsi+100h]; this
0x180075476  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007547b  mov     r9d, eax
0x18007547e  mov     [rsp+68h+var_48], 0B5Ah
0x180075486  lea     r8, aCconnectionGet_22; "<CConnection::getKeywords|ADO|ERR> %u#,"...
0x18007548d  mov     edx, 2D6809h
0x180075492  jmp     loc_18007516F
0x180075497  mov     r9d, 0B5Ah
0x18007549d  mov     edx, 2D6809h
0x1800754a2  jmp     short loc_1800754F1
0x1800754a4  test    byte ptr cs:_bidGblFlags, 2
0x1800754ab  jz      short loc_180075504
0x1800754ad  lea     rcx, [rsi+100h]; this
0x1800754b4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800754b9  cmp     eax, 0FFFFFFFFh
0x1800754bc  jz      short loc_1800754E6
0x1800754be  lea     rcx, [rsi+100h]; this
0x1800754c5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800754ca  mov     r9d, eax
0x1800754cd  mov     [rsp+68h+var_48], 0B1Dh
0x1800754d5  lea     r8, aCconnectionGet_22; "<CConnection::getKeywords|ADO|ERR> %u#,"...
0x1800754dc  mov     edx, 2C7409h
0x1800754e1  jmp     loc_18007516F
0x1800754e6  mov     r9d, 0B1Dh
0x1800754ec  mov     edx, 2C7409h
0x1800754f1  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800754f8  lea     r8, aCconnectionGet_11; "<CConnection::getKeywords|ADO|ERR>  lin"...
0x1800754ff  call    _bidTraceW
0x180075504  mov     rcx, [rsp+68h+Str]; pv
0x180075509  test    rcx, rcx
0x18007550c  jz      short loc_18007551A
0x18007550e  call    cs:__imp_CoTaskMemFree
0x180075515  nop     dword ptr [rax+rax+00h]
0x18007551a  mov     rcx, [rsp+68h+arg_8]
0x18007551f  test    rcx, rcx
0x180075522  jz      short loc_180075530
0x180075524  mov     rax, [rcx]
0x180075527  mov     rax, [rax+10h]
0x18007552b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075530  mov     eax, ebx
0x180075532  mov     rbx, [rsp+68h+arg_18]
0x18007553a  add     rsp, 30h
0x18007553e  pop     r15
0x180075540  pop     r14
0x180075542  pop     r13
0x180075544  pop     r12
0x180075546  pop     rdi
0x180075547  pop     rsi
0x180075548  pop     rbp
0x180075549  retn
```
