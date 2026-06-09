# CMEnumerateProviders(uint &,CCMProviderEnumInformation * &)

- ea: `0x1800168e4`
- end: `0x180016cea`
- name: `?CMEnumerateProviders@@YAJAEAIAEAPEAUCCMProviderEnumInformation@@@Z`
- size: `1030`
- prototype: `__int64 __fastcall(unsigned int *, struct CCMProviderEnumInformation **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180056df4`

## callees

- `0x1800112b0`
- `0x180011bcc`
- `0x180013870`
- `0x1800168e4`
- `0x180016cf0`
- `0x180029560`
- `0x18002b2bc`
- `0x18002b35c`
- `0x18002ec0c`
- `0x18002ec26`
- `0x18005658c`
- `0x18007e6ca`
- `0x18007e700`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180016961`
- `MSDART!MpHeapAlloc` at `0x180016aee`
- `MSDART!MpHeapAlloc` at `0x180016961`
- `MSDART!MpHeapAlloc` at `0x180016aee`
- `ole32!CLSIDFromString` at `0x180016bb7`
- `ole32!CLSIDFromString` at `0x180016bb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMEnumerateProviders(unsigned int *a1, struct CCMProviderEnumInformation **a2)
{
  char *v4; // rsi
  unsigned int v5; // r14d
  unsigned int v6; // edi
  unsigned int v7; // r12d
  __int64 v8; // rax
  char *v9; // rbx
  char v10; // al
  int v11; // ebx
  size_t v12; // r14
  unsigned __int64 v13; // r12
  int v14; // ebx
  unsigned int v15; // ebx
  __int64 v16; // rax
  struct CCMProviderEnumInformation *v17; // rax
  struct CCMProviderEnumInformation *v18; // rdi
  char v19; // al
  int v20; // ebx
  unsigned int i; // r14d
  __int64 v22; // r12
  __int64 v23; // rbx
  char *v24; // rdi
  unsigned int v25; // r11d
  void **v27; // rbx
  int v28; // eax
  int v29; // [rsp+20h] [rbp-128h]
  int pExceptionObject; // [rsp+24h] [rbp-124h] BYREF
  int v31; // [rsp+28h] [rbp-120h] BYREF
  int v32; // [rsp+2Ch] [rbp-11Ch] BYREF
  char *v33; // [rsp+30h] [rbp-118h]
  void **v34; // [rsp+38h] [rbp-110h]
  struct CCMProviderEnumInformation *v35; // [rsp+40h] [rbp-108h]
  char v36[8]; // [rsp+50h] [rbp-F8h] BYREF
  char v37[8]; // [rsp+58h] [rbp-F0h] BYREF
  char v38[8]; // [rsp+60h] [rbp-E8h] BYREF
  char v39[8]; // [rsp+68h] [rbp-E0h] BYREF
  char v40[160]; // [rsp+70h] [rbp-D8h] BYREF

  v34 = (void **)a2;
  v4 = 0;
  v33 = 0;
  v5 = 0;
  COledbEnum::COledbEnum((COledbEnum *)v36);
  v6 = 0;
  try
  {
    while ( 1 )
    {
      if ( v6 == v5 )
      {
        v7 = v5 + 15;
        v8 = 2088LL * (v5 + 15);
        if ( !is_mul_ok(v5 + 15, 0x828u) )
          v8 = -1;
        v9 = (char *)MpHeapAlloc(g_hHeapHandle, 19922944, v8);
        if ( !v9 )
        {
          v10 = bidGblFlags;
          v11 = -2147024882;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024882, L"<CMEnumerateProviders|OLEDB|ERR> ", 0x97u);
            v10 = bidGblFlags;
          }
          if ( (v10 & 2) != 0 )
            v11 = bidTraceHR(off_1800C83F8[0], 154633, L"<CMEnumerateProviders|Trace|HR> ", 2147942414LL);
          pExceptionObject = v11;
          throw (long *)&pExceptionObject;
        }
        v12 = 2088LL * v5;
        memset_0(&v9[v12], 0, 0x7A58u);
        if ( v4 )
          memcpy_0(v9, v4, v12);
        operator delete(v4);
        v5 = v7;
        v4 = v9;
        v33 = v9;
      }
      v13 = v6;
      v14 = COledbEnum::Next((COledbEnum *)v36, (struct RowBinding *)&v4[2088 * v6]);
      if ( v14 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v14, L"<CMEnumerateProviders|OLEDB|ERR> ", 0xA5u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v14, L"<CMEnumerateProviders|OLEDB|ERR> ", 0xA5u);
            if ( (bidGblFlags & 2) != 0 )
              v14 = bidTraceHR(off_1800C83F8[0], 168969, L"<CMEnumerateProviders|Trace|HR> ", (unsigned int)v14);
          }
        }
        v31 = v14;
        throw (long *)&v31;
      }
      if ( v14 == 1 )
        break;
      ++v6;
    }
    v15 = 0;
    v29 = 0;
    if ( v6 )
    {
      *a1 = v6;
      v16 = 1048LL * v6;
      if ( !is_mul_ok(v6, 0x418u) )
        v16 = -1;
      v17 = (struct CCMProviderEnumInformation *)MpHeapAlloc(g_hHeapHandle, 19922944, v16);
      v18 = v17;
      v35 = v17;
      if ( v17 )
        `vector constructor iterator'(
          v17,
          0x418u,
          v13,
          (void *(*)(void *))CCMProviderEnumInformation::CCMProviderEnumInformation);
      else
        v18 = 0;
      *a2 = v18;
      if ( !v18 )
      {
        v19 = bidGblFlags;
        v20 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024882, L"<CMEnumerateProviders|OLEDB|ERR> ", 0xB4u);
          v19 = bidGblFlags;
        }
        if ( (v19 & 2) != 0 )
          v20 = bidTraceHR(off_1800C83F8[0], 184329, L"<CMEnumerateProviders|Trace|HR> ", 2147942414LL);
        v32 = v20;
        throw (long *)&v32;
      }
      for ( i = 0; i < *a1; ++i )
      {
        v22 = 1048LL * i;
        v23 = 2088LL * i;
        v24 = &v4[v23];
        CLSIDFromString((LPCOLESTR)&v4[v23 + 1564], (LPCLSID)((char *)*a2 + v22));
        StringCchCopyW((unsigned __int16 *)((char *)*a2 + v22 + 16), 0x100u, (const unsigned __int16 *)&v4[v23]);
        v15 = StringCchCopyW(
                (unsigned __int16 *)((char *)*a2 + v22 + 528),
                v25,
                (const unsigned __int16 *)&v4[v23 + 1040]);
        v29 = v15;
        *(_WORD *)((char *)*a2 + v22 + 1040) = *((_WORD *)v24 + 780);
        if ( ((*((_WORD *)v24 + 780) - 1) & 0xFFFD) == 0 )
          *(_DWORD *)((char *)*a2 + v22 + 1044) = 1;
      }
    }
    HKAuto::~HKAuto((HKAuto *)v40);
    HKAuto::~HKAuto((HKAuto *)v39);
    HKAuto::~HKAuto((HKAuto *)v38);
    HKAuto::~HKAuto((HKAuto *)v37);
    HKAuto::~HKAuto((HKAuto *)v36);
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8880[0] )
      bidTraceA(off_1800C83F8[0], 221184, off_1800C8880[0], 0);
    v27 = v34;
    operator delete(*v34);
    *v27 = 0;
    v28 = v29;
    if ( v29 >= 0 )
      v28 = -2147467259;
    v15 = v28;
    v4 = v33;
  }
  if ( v4 )
    operator delete(v4);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C83F8[0], 234505, L"<CMEnumerateProviders|Trace|HR> ", v15);
  return v15;
}

```

## disassembly

```asm
0x1800168e4  mov     [rsp+arg_10], rbx
0x1800168e9  mov     [rsp+arg_18], rsi
0x1800168ee  push    rdi
0x1800168ef  push    r12
0x1800168f1  push    r13
0x1800168f3  push    r14
0x1800168f5  push    r15
0x1800168f7  sub     rsp, 120h
0x1800168fe  mov     rax, cs:__security_cookie
0x180016905  xor     rax, rsp
0x180016908  mov     [rsp+148h+var_38], rax
0x180016910  mov     r15, rdx
0x180016913  mov     r13, rcx
0x180016916  mov     [rsp+148h+var_110], rdx
0x18001691b  xor     esi, esi
0x18001691d  mov     [rsp+148h+var_118], rsi
0x180016922  xor     r14d, r14d
0x180016925  lea     rcx, [rsp+148h+var_F8]; this
0x18001692a  call    ??0COledbEnum@@QEAA@XZ; COledbEnum::COledbEnum(void)
0x18001692f  nop
0x180016930  xor     edi, edi
0x180016932  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016936  cmp     edi, r14d
0x180016939  jnz     loc_180016A13
0x18001693f  lea     r12d, [r14+0Fh]
0x180016943  mov     ecx, r12d
0x180016946  mov     eax, 828h
0x18001694b  mul     rcx
0x18001694e  cmovb   rax, r8
0x180016952  mov     r8, rax
0x180016955  mov     edx, 1300000h
0x18001695a  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180016961  call    cs:__imp_MpHeapAlloc
0x180016967  mov     rbx, rax
0x18001696a  test    rax, rax
0x18001696d  jnz     short loc_1800169D2
0x18001696f  mov     eax, cs:_bidGblFlags
0x180016975  mov     ebx, 8007000Eh
0x18001697a  test    al, 2
0x18001697c  jz      short loc_180016998
0x18001697e  mov     r8d, 97h; unsigned int
0x180016984  lea     rdx, aCmenumeratepro; "<CMEnumerateProviders|OLEDB|ERR> "
0x18001698b  mov     ecx, ebx; int
0x18001698d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180016992  mov     eax, cs:_bidGblFlags
0x180016998  mov     [rsp+148h+var_128], ebx
0x18001699c  test    al, 2
0x18001699e  jz      short loc_1800169BD
0x1800169a0  mov     r9d, ebx
0x1800169a3  lea     r8, aCmenumeratepro_0; "<CMEnumerateProviders|Trace|HR> "
0x1800169aa  mov     edx, 25C09h
0x1800169af  mov     rcx, cs:off_1800C83F8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800169b6  call    _bidTraceHR
0x1800169bb  mov     ebx, eax
0x1800169bd  mov     [rsp+148h+pExceptionObject], ebx
0x1800169c1  lea     rdx, _TI1J; pThrowInfo
0x1800169c8  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x1800169cd  call    _CxxThrowException_0
0x1800169d2  mov     eax, r14d
0x1800169d5  imul    r14, rax, 828h
0x1800169dc  lea     rcx, [r14+rbx]; void *
0x1800169e0  xor     edx, edx; Val
0x1800169e2  mov     r8d, 7A58h; Size
0x1800169e8  call    memset_0
0x1800169ed  test    rsi, rsi
0x1800169f0  jz      short loc_180016A00
0x1800169f2  mov     r8, r14; Size
0x1800169f5  mov     rdx, rsi; Src
0x1800169f8  mov     rcx, rbx; void *
0x1800169fb  call    memcpy_0
0x180016a00  mov     rcx, rsi; void *
0x180016a03  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016a08  mov     r14d, r12d
0x180016a0b  mov     rsi, rbx
0x180016a0e  mov     [rsp+148h+var_118], rbx
0x180016a13  mov     r12d, edi
0x180016a16  imul    rdx, r12, 828h
0x180016a1d  add     rdx, rsi; struct RowBinding *
0x180016a20  lea     rcx, [rsp+148h+var_F8]; this
0x180016a25  call    ?Next@COledbEnum@@QEAAJPEAURowBinding@@@Z; COledbEnum::Next(RowBinding *)
0x180016a2a  mov     ebx, eax
0x180016a2c  mov     [rsp+148h+var_128], eax
0x180016a30  test    eax, eax
0x180016a32  jns     short loc_180016AAC
0x180016a34  mov     eax, cs:_bidGblFlags
0x180016a3a  test    al, 2
0x180016a3c  jz      short loc_180016A97
0x180016a3e  mov     r8d, 0A5h; unsigned int
0x180016a44  lea     rdx, aCmenumeratepro; "<CMEnumerateProviders|OLEDB|ERR> "
0x180016a4b  mov     ecx, ebx; int
0x180016a4d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180016a52  mov     eax, cs:_bidGblFlags
0x180016a58  test    al, 2
0x180016a5a  jz      short loc_180016A97
0x180016a5c  mov     r8d, 0A5h; unsigned int
0x180016a62  lea     rdx, aCmenumeratepro; "<CMEnumerateProviders|OLEDB|ERR> "
0x180016a69  mov     ecx, ebx; int
0x180016a6b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180016a70  mov     eax, cs:_bidGblFlags
0x180016a76  test    al, 2
0x180016a78  jz      short loc_180016A97
0x180016a7a  mov     r9d, ebx
0x180016a7d  lea     r8, aCmenumeratepro_0; "<CMEnumerateProviders|Trace|HR> "
0x180016a84  mov     edx, 29409h
0x180016a89  mov     rcx, cs:off_1800C83F8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180016a90  call    _bidTraceHR
0x180016a95  mov     ebx, eax
0x180016a97  mov     [rsp+148h+var_120], ebx
0x180016a9b  lea     rdx, _TI1J; pThrowInfo
0x180016aa2  lea     rcx, [rsp+148h+var_120]; pExceptionObject
0x180016aa7  call    _CxxThrowException_0
0x180016aac  mov     eax, 1
0x180016ab1  cmp     ebx, eax
0x180016ab3  jnz     loc_180016CE1
0x180016ab9  xor     ebx, ebx
0x180016abb  mov     [rsp+148h+var_128], ebx
0x180016abf  test    edi, edi
0x180016ac1  jz      loc_180016C41
0x180016ac7  mov     [r13+0], edi
0x180016acb  mov     r14d, 418h
0x180016ad1  mov     eax, r14d
0x180016ad4  mul     r12
0x180016ad7  lea     rcx, [rbx-1]
0x180016adb  cmovb   rax, rcx
0x180016adf  mov     r8, rax
0x180016ae2  mov     edx, 1300000h
0x180016ae7  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180016aee  call    cs:__imp_MpHeapAlloc
0x180016af4  mov     rdi, rax
0x180016af7  mov     [rsp+148h+var_108], rax
0x180016afc  test    rax, rax
0x180016aff  jz      short loc_180016B18
0x180016b01  lea     r9, ??0CCMProviderEnumInformation@@QEAA@XZ; void *(*)(void *)
0x180016b08  mov     r8, r12; unsigned __int64
0x180016b0b  mov     edx, r14d; unsigned __int64
0x180016b0e  mov     rcx, rax; void *
0x180016b11  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180016b16  jmp     short loc_180016B1A
0x180016b18  xor     edi, edi
0x180016b1a  mov     [r15], rdi
0x180016b1d  test    rdi, rdi
0x180016b20  jnz     short loc_180016B85
0x180016b22  mov     eax, cs:_bidGblFlags
0x180016b28  mov     ebx, 8007000Eh
0x180016b2d  test    al, 2
0x180016b2f  jz      short loc_180016B4B
0x180016b31  mov     r8d, 0B4h; unsigned int
0x180016b37  lea     rdx, aCmenumeratepro; "<CMEnumerateProviders|OLEDB|ERR> "
0x180016b3e  mov     ecx, ebx; int
0x180016b40  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180016b45  mov     eax, cs:_bidGblFlags
0x180016b4b  mov     [rsp+148h+var_128], ebx
0x180016b4f  test    al, 2
0x180016b51  jz      short loc_180016B70
0x180016b53  mov     r9d, ebx
0x180016b56  lea     r8, aCmenumeratepro_0; "<CMEnumerateProviders|Trace|HR> "
0x180016b5d  mov     edx, 2D009h
0x180016b62  mov     rcx, cs:off_1800C83F8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180016b69  call    _bidTraceHR
0x180016b6e  mov     ebx, eax
0x180016b70  mov     [rsp+148h+var_11C], ebx
0x180016b74  lea     rdx, _TI1J; pThrowInfo
0x180016b7b  lea     rcx, [rsp+148h+var_11C]; pExceptionObject
0x180016b80  call    _CxxThrowException_0
0x180016b85  xor     r14d, r14d
0x180016b88  cmp     [r13+0], r14d
0x180016b8c  jbe     loc_180016C41
0x180016b92  mov     eax, r14d
0x180016b95  imul    r12, rax, 418h
0x180016b9c  imul    rbx, rax, 828h
0x180016ba3  lea     rdi, [rbx+rsi]
0x180016ba7  mov     rdx, [r15]
0x180016baa  add     rdx, r12; pclsid
0x180016bad  lea     rcx, [rbx+61Ch]
0x180016bb4  add     rcx, rsi; lpsz
0x180016bb7  call    cs:__imp_CLSIDFromString
0x180016bbd  mov     rcx, [r15]
0x180016bc0  add     rcx, 10h
0x180016bc4  add     rcx, r12; unsigned __int16 *
0x180016bc7  mov     r8, rdi; unsigned __int16 *
0x180016bca  mov     r11d, 100h
0x180016bd0  mov     edx, r11d; unsigned __int64
0x180016bd3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016bd8  lea     r8, [rbx+410h]
0x180016bdf  add     r8, rsi; unsigned __int16 *
0x180016be2  mov     rcx, [r15]
0x180016be5  add     rcx, 210h
0x180016bec  add     rcx, r12; unsigned __int16 *
0x180016bef  mov     edx, r11d; unsigned __int64
0x180016bf2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016bf7  mov     ebx, eax
0x180016bf9  mov     [rsp+148h+var_128], eax
0x180016bfd  mov     rdx, [r15]
0x180016c00  movzx   ecx, word ptr [rdi+618h]
0x180016c07  mov     [r12+rdx+410h], cx
0x180016c10  movzx   ecx, word ptr [rdi+618h]
0x180016c17  mov     edx, 1
0x180016c1c  sub     cx, dx
0x180016c1f  mov     eax, 0FFFDh
0x180016c24  test    ax, cx
0x180016c27  jnz     short loc_180016C34
0x180016c29  mov     rcx, [r15]
0x180016c2c  mov     [r12+rcx+414h], edx
0x180016c34  add     r14d, edx
0x180016c37  cmp     r14d, [r13+0]
0x180016c3b  jb      loc_180016B92
0x180016c41  lea     rcx, [rsp+148h+var_D8]; this
0x180016c46  call    ??1HKAuto@@QEAA@XZ; HKAuto::~HKAuto(void)
0x180016c4b  lea     rcx, [rsp+148h+var_E0]; this
0x180016c50  call    ??1HKAuto@@QEAA@XZ; HKAuto::~HKAuto(void)
0x180016c55  lea     rcx, [rsp+148h+var_E8]; this
0x180016c5a  call    ??1HKAuto@@QEAA@XZ; HKAuto::~HKAuto(void)
0x180016c5f  lea     rcx, [rsp+148h+var_F0]; this
0x180016c64  call    ??1HKAuto@@QEAA@XZ; HKAuto::~HKAuto(void)
0x180016c69  lea     rcx, [rsp+148h+var_F8]; this
0x180016c6e  call    ??1HKAuto@@QEAA@XZ; HKAuto::~HKAuto(void)
0x180016c73  nop
0x180016c74  jmp     short loc_180016C7F
0x180016c76  mov     ebx, [rsp+148h+var_128]
0x180016c7a  mov     rsi, [rsp+148h+var_118]
0x180016c7f  test    rsi, rsi
0x180016c82  jz      short loc_180016C8C
0x180016c84  mov     rcx, rsi; void *
0x180016c87  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016c8c  test    byte ptr cs:_bidGblFlags, 2
0x180016c93  jz      short loc_180016CB2
0x180016c95  mov     r9d, ebx
0x180016c98  lea     r8, aCmenumeratepro_0; "<CMEnumerateProviders|Trace|HR> "
0x180016c9f  mov     edx, 39409h
0x180016ca4  mov     rcx, cs:off_1800C83F8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180016cab  call    _bidTraceHR
0x180016cb0  mov     ebx, eax
0x180016cb2  mov     eax, ebx
0x180016cb4  mov     rcx, [rsp+148h+var_38]
0x180016cbc  xor     rcx, rsp; StackCookie
0x180016cbf  call    __security_check_cookie
0x180016cc4  lea     r11, [rsp+148h+var_28]
0x180016ccc  mov     rbx, [r11+40h]
0x180016cd0  mov     rsi, [r11+48h]
0x180016cd4  mov     rsp, r11
0x180016cd7  pop     r15
0x180016cd9  pop     r14
0x180016cdb  pop     r13
0x180016cdd  pop     r12
0x180016cdf  pop     rdi
0x180016ce0  retn
0x180016ce1  add     edi, eax
0x180016ce3  jmp     loc_180016932
```
