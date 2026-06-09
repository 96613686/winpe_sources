# SrvCryptEnumAlgorithms

- ea: `0x180002800`
- end: `0x180002d0f`
- name: `SrvCryptEnumAlgorithms`
- size: `1295`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x1800025b0`
- `0x180002800`
- `0x180002d20`
- `0x180002d40`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180005510`
- `0x180006280`
- `0x180018928`
- `0x180019010`

## string_xrefs

- `0x180002856`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x1800029ae`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002a16`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002a64`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002b66`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002bea`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002c83`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002c9e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002cf7`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptEnumAlgorithms(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int *a4,
        wchar_t ***a5,
        int a6)
{
  int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // r13
  __int64 v11; // rax
  wchar_t ***v12; // rsi
  int v13; // edx
  unsigned int v14; // ebx
  int v16; // eax
  unsigned __int128 v17; // rax
  size_t v18; // rbx
  wchar_t **v19; // rax
  int v20; // edx
  wchar_t **v21; // r15
  int v22; // eax
  STRSAFE_LPCWSTR *v23; // rbx
  wchar_t **v24; // r14
  unsigned int i; // ebp
  STRSAFE_LPCWSTR v26; // rax
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // edx
  size_t v30; // r12
  wchar_t *v31; // rax
  HRESULT v32; // eax
  int v33; // edx
  __int64 v34; // r9
  wchar_t **v35; // r14
  wchar_t **v36; // rsi
  unsigned int j; // ebp
  __int64 v38; // r9
  __int64 v39; // rcx
  char v40; // [rsp+30h] [rbp-68h]
  void *Src; // [rsp+A0h] [rbp+8h] BYREF

  Src = 0;
  if ( !a1 )
  {
    v8 = -2146893786;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v8;
    v10 = 0;
    v40 = -79;
LABEL_5:
    WPP_SF_sDsd(
      v9[2],
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
      v40);
    goto LABEL_14;
  }
  v11 = SrvLookupAndReferenceProvider(a1, a2, 0);
  v10 = v11;
  if ( !v11 )
  {
    v8 = -2146893786;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v40 = -70;
    goto LABEL_5;
  }
  if ( !a4 || (v12 = a5) == 0 )
  {
    v8 = -2146893785;
    v38 = 961;
    v39 = 2148073511LL;
    goto LABEL_73;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, void **, int))(v11 + 168))(
          *(_QWORD *)(v11 + 296),
          a3,
          a4,
          &Src,
          a6);
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        (unsigned int)"Status",
        v14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        210);
    v8 = NormalizeNteStatus(v14);
    goto LABEL_14;
  }
  if ( !*a4 )
  {
    v8 = -2146893792;
    v38 = 1105;
    v39 = 2148073504LL;
LABEL_73:
    DebugTraceError(v39, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v38);
    goto LABEL_14;
  }
  v17 = 0x18 * (unsigned __int128)*a4;
  v18 = 24LL * *a4;
  if ( !is_mul_ok(0x18u, *a4) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        DWORD2(v17),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        (unsigned int)"hr",
        22,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        249);
    goto LABEL_32;
  }
  if ( v18 > 0xFFFFFFFF )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        DWORD2(v17),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        (unsigned int)"hr",
        22,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        2);
LABEL_32:
    v8 = -2146893792;
    goto LABEL_14;
  }
  v19 = (wchar_t **)MSCryptAlloc((unsigned int)v18);
  v21 = v19;
  if ( !v19 )
  {
    v8 = -2146893810;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        12);
    goto LABEL_14;
  }
  memcpy_0(v19, Src, v18);
  v23 = (STRSAFE_LPCWSTR *)Src;
  v24 = v21;
  for ( i = 0; ; ++i )
  {
    if ( i >= *a4 )
    {
      *v12 = v21;
      v8 = 0;
      goto LABEL_14;
    }
    v26 = *v23;
    if ( !*v23 )
    {
      v29 = -2147024809;
LABEL_65:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v29,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          (unsigned int)"hr",
          v29,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          33);
      goto LABEL_50;
    }
    v27 = 512;
    do
    {
      if ( !*v26 )
        break;
      ++v26;
      --v27;
    }
    while ( v27 );
    v28 = (512 - v27) & -(__int64)(v27 != 0);
    v29 = v27 == 0 ? 0x80070057 : 0;
    if ( !v27 )
      goto LABEL_65;
    v30 = v28 + 1;
    if ( !is_mul_ok(v28 + 1, 2u) )
    {
      v34 = 1066;
LABEL_49:
      DebugTraceError(2147942934LL, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v34);
LABEL_50:
      v8 = -2146893792;
      goto LABEL_51;
    }
    if ( (unsigned __int64)(2 * (v28 + 1)) > 0xFFFFFFFF )
    {
      v34 = 1075;
      goto LABEL_49;
    }
    v31 = (wchar_t *)MSCryptAlloc((unsigned int)(2 * (v28 + 1)));
    *v24 = v31;
    if ( !v31 )
      break;
    v32 = StringCchCopyW(v31, v30, *v23);
    if ( v32 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v33,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          (unsigned int)"hr",
          v32,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          69);
      goto LABEL_50;
    }
    v23 += 3;
    v24 += 3;
  }
  v8 = -2146893810;
  DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 1085);
LABEL_51:
  v35 = v21;
  v36 = (wchar_t **)Src;
  for ( j = 0; j < *a4; ++j )
  {
    if ( *v35 != *v36 )
      MSCryptFree(*v35);
    v35 += 3;
    v36 += 3;
  }
  MSCryptFree(v21);
LABEL_14:
  if ( Src )
  {
    v22 = (*(__int64 (**)(void))(v10 + 136))();
    if ( v22 < 0 && v8 >= 0 )
      v8 = NormalizeNteStatus((unsigned int)v22);
  }
  if ( v10 )
  {
    v16 = SrvDereferenceProvider(v10);
    if ( v16 < 0 && v8 >= 0 )
      return (unsigned int)v16;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002800  mov     rax, rsp
0x180002803  push    rbx
0x180002804  push    rbp
0x180002805  push    rsi
0x180002806  push    rdi
0x180002807  push    r12
0x180002809  push    r13
0x18000280b  push    r14
0x18000280d  push    r15
0x18000280f  sub     rsp, 58h
0x180002813  xor     r12d, r12d
0x180002816  mov     rdi, r9
0x180002819  mov     [rax+8], r12
0x18000281d  mov     ebx, r8d
0x180002820  test    rcx, rcx
0x180002823  jnz     short loc_18000287F
0x180002825  mov     ebx, 80090026h
0x18000282a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002831  lea     rax, WPP_GLOBAL_Control
0x180002838  cmp     rcx, rax
0x18000283b  jz      loc_18000291A
0x180002841  test    byte ptr [rcx+1Ch], 1
0x180002845  jz      loc_18000291A
0x18000284b  mov     r13d, r12d
0x18000284e  mov     dword ptr [rsp+98h+var_68], 3B1h
0x180002856  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000285d  mov     [rsp+98h+var_70], r8
0x180002862  mov     [rsp+98h+var_78], 80090026h
0x18000286a  mov     rcx, [rcx+10h]
0x18000286e  lea     r9, aStatus; "Status"
0x180002875  call    WPP_SF_sDsd
0x18000287a  jmp     loc_180002904
0x18000287f  xor     r8d, r8d
0x180002882  call    SrvLookupAndReferenceProvider
0x180002887  mov     r13, rax
0x18000288a  test    rax, rax
0x18000288d  jz      loc_180002C10
0x180002893  test    rdi, rdi
0x180002896  jz      loc_180002CE7
0x18000289c  mov     rsi, [rsp+98h+arg_20]
0x1800028a4  test    rsi, rsi
0x1800028a7  jz      loc_180002CE7
0x1800028ad  mov     eax, [rsp+98h+arg_28]
0x1800028b4  lea     r9, [rsp+98h+Src]
0x1800028bc  mov     rcx, [r13+128h]
0x1800028c3  mov     r8, rdi
0x1800028c6  mov     [rsp+98h+var_78], eax
0x1800028ca  mov     edx, ebx
0x1800028cc  mov     rax, [r13+0A8h]
0x1800028d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d8  mov     ebx, eax
0x1800028da  test    eax, eax
0x1800028dc  jz      short loc_180002940
0x1800028de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028e5  lea     rax, WPP_GLOBAL_Control
0x1800028ec  cmp     rcx, rax
0x1800028ef  jz      short loc_1800028FB
0x1800028f1  test    byte ptr [rcx+1Ch], 1
0x1800028f5  jnz     loc_180002A12
0x1800028fb  mov     ecx, ebx
0x1800028fd  call    NormalizeNteStatus
0x180002902  mov     ebx, eax
0x180002904  mov     rcx, [rsp+98h+Src]
0x18000290c  test    rcx, rcx
0x18000290f  jnz     loc_1800029C7
0x180002915  test    r13, r13
0x180002918  jnz     short loc_18000292D
0x18000291a  mov     eax, ebx
0x18000291c  add     rsp, 58h
0x180002920  pop     r15
0x180002922  pop     r14
0x180002924  pop     r13
0x180002926  pop     r12
0x180002928  pop     rdi
0x180002929  pop     rsi
0x18000292a  pop     rbp
0x18000292b  pop     rbx
0x18000292c  retn
0x18000292d  mov     rcx, r13
0x180002930  call    SrvDereferenceProvider
0x180002935  test    eax, eax
0x180002937  jns     short loc_18000291A
0x180002939  test    ebx, ebx
0x18000293b  cmovns  ebx, eax
0x18000293e  jmp     short loc_18000291A
0x180002940  cmp     [rdi], r12d
0x180002943  jbe     loc_180002CD5
0x180002949  mov     eax, [rdi]
0x18000294b  mov     ecx, 18h
0x180002950  mul     rcx
0x180002953  mov     rbx, rax
0x180002956  test    rdx, rdx
0x180002959  jnz     loc_180002A3F
0x18000295f  mov     eax, 0FFFFFFFFh
0x180002964  cmp     rbx, rax
0x180002967  ja      loc_1800029F1
0x18000296d  mov     ecx, ebx
0x18000296f  call    MSCryptAlloc
0x180002974  mov     r15, rax
0x180002977  test    rax, rax
0x18000297a  jnz     loc_180002A86
0x180002980  mov     ebx, 8009000Eh
0x180002985  mov     rcx, cs:WPP_GLOBAL_Control
0x18000298c  lea     rax, WPP_GLOBAL_Control
0x180002993  cmp     rcx, rax
0x180002996  jz      loc_180002904
0x18000299c  test    byte ptr [rcx+1Ch], 1
0x1800029a0  jz      loc_180002904
0x1800029a6  mov     dword ptr [rsp+98h+var_68], 40Ch
0x1800029ae  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800029b5  mov     [rsp+98h+var_70], r8
0x1800029ba  mov     [rsp+98h+var_78], 8009000Eh
0x1800029c2  jmp     loc_18000286A
0x1800029c7  mov     rax, [r13+88h]
0x1800029ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d3  test    eax, eax
0x1800029d5  jns     loc_180002915
0x1800029db  test    ebx, ebx
0x1800029dd  js      loc_180002915
0x1800029e3  mov     ecx, eax
0x1800029e5  call    NormalizeNteStatus
0x1800029ea  mov     ebx, eax
0x1800029ec  jmp     loc_180002915
0x1800029f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029f8  lea     rax, WPP_GLOBAL_Control
0x1800029ff  cmp     rcx, rax
0x180002a02  jnz     loc_180002C43
0x180002a08  mov     ebx, 80090020h
0x180002a0d  jmp     loc_180002904
0x180002a12  mov     rcx, [rcx+10h]
0x180002a16  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002a1d  mov     dword ptr [rsp+98h+var_68], 3D2h
0x180002a25  lea     r9, aStatus; "Status"
0x180002a2c  mov     [rsp+98h+var_70], r8
0x180002a31  mov     [rsp+98h+var_78], ebx
0x180002a35  call    WPP_SF_sDsd
0x180002a3a  jmp     loc_1800028FB
0x180002a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a46  lea     rax, WPP_GLOBAL_Control
0x180002a4d  cmp     rcx, rax
0x180002a50  jz      short loc_180002A08
0x180002a52  test    byte ptr [rcx+1Ch], 1
0x180002a56  jz      short loc_180002A08
0x180002a58  mov     dword ptr [rsp+98h+var_68], 3F9h
0x180002a60  mov     rcx, [rcx+10h]
0x180002a64  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002a6b  mov     [rsp+98h+var_70], r8
0x180002a70  lea     r9, aHr; "hr"
0x180002a77  mov     [rsp+98h+var_78], 80070216h
0x180002a7f  call    WPP_SF_sDsd
0x180002a84  jmp     short loc_180002A08
0x180002a86  mov     rdx, [rsp+98h+Src]; Src
0x180002a8e  mov     r8, rbx; Size
0x180002a91  mov     rcx, r15; void *
0x180002a94  call    memcpy_0
0x180002a99  mov     rbx, [rsp+98h+Src]
0x180002aa1  mov     r14, r15
0x180002aa4  mov     ebp, r12d
0x180002aa7  cmp     ebp, [rdi]
0x180002aa9  jnb     loc_180002CCA
0x180002aaf  mov     rax, [rbx]
0x180002ab2  test    rax, rax
0x180002ab5  jz      loc_180002CC3
0x180002abb  mov     r8d, 200h
0x180002ac1  cmp     [rax], r12w
0x180002ac5  jz      short loc_180002AD1
0x180002ac7  add     rax, 2
0x180002acb  sub     r8, 1
0x180002acf  jnz     short loc_180002AC1
0x180002ad1  mov     ecx, 200h
0x180002ad6  mov     rax, r8
0x180002ad9  sub     rcx, r8
0x180002adc  neg     rax
0x180002adf  mov     rax, r8
0x180002ae2  sbb     r9, r9
0x180002ae5  and     r9, rcx
0x180002ae8  neg     rax
0x180002aeb  sbb     edx, edx
0x180002aed  not     edx
0x180002aef  and     edx, 80070057h
0x180002af5  test    r8, r8
0x180002af8  jz      loc_180002C5A
0x180002afe  lea     r12, [r9+1]
0x180002b02  mov     [rsp+98h+var_58], 0
0x180002b0b  mov     eax, 2
0x180002b10  mul     r12
0x180002b13  test    rdx, rdx
0x180002b16  jnz     loc_180002BC1
0x180002b1c  mov     ecx, 0FFFFFFFFh
0x180002b21  cmp     rax, rcx
0x180002b24  ja      short loc_180002B60
0x180002b26  mov     ecx, eax
0x180002b28  call    MSCryptAlloc
0x180002b2d  mov     [r14], rax
0x180002b30  test    rax, rax
0x180002b33  jz      loc_180002C98
0x180002b39  mov     r8, [rbx]; pszSrc
0x180002b3c  mov     rdx, r12; cchDest
0x180002b3f  mov     rcx, rax; pszDest
0x180002b42  call    StringCchCopyW
0x180002b47  xor     r12d, r12d
0x180002b4a  mov     r11d, eax
0x180002b4d  test    eax, eax
0x180002b4f  js      short loc_180002BC9
0x180002b51  add     rbx, 18h
0x180002b55  add     r14, 18h
0x180002b59  inc     ebp
0x180002b5b  jmp     loc_180002AA7
0x180002b60  mov     r9d, 433h
0x180002b66  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002b6d  mov     ecx, 80070216h
0x180002b72  lea     rdx, aHr; "hr"
0x180002b79  call    DebugTraceError
0x180002b7e  xor     r12d, r12d
0x180002b81  mov     ebx, 80090020h
0x180002b86  mov     r14, r15
0x180002b89  mov     rsi, [rsp+98h+Src]
0x180002b91  mov     ebp, r12d
0x180002b94  cmp     [rdi], r12d
0x180002b97  jbe     short loc_180002BB4
0x180002b99  mov     rcx, [r14]
0x180002b9c  cmp     rcx, [rsi]
0x180002b9f  jz      short loc_180002BA6
0x180002ba1  call    MSCryptFree
0x180002ba6  add     r14, 18h
0x180002baa  add     rsi, 18h
0x180002bae  inc     ebp
0x180002bb0  cmp     ebp, [rdi]
0x180002bb2  jb      short loc_180002B99
0x180002bb4  mov     rcx, r15
0x180002bb7  call    MSCryptFree
0x180002bbc  jmp     loc_180002904
0x180002bc1  mov     r9d, 42Ah
0x180002bc7  jmp     short loc_180002B66
0x180002bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bd0  lea     rax, WPP_GLOBAL_Control
0x180002bd7  cmp     rcx, rax
0x180002bda  jz      short loc_180002B81
0x180002bdc  test    byte ptr [rcx+1Ch], 1
0x180002be0  jz      short loc_180002B81
0x180002be2  mov     dword ptr [rsp+98h+var_68], 445h
0x180002bea  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002bf1  mov     [rsp+98h+var_70], r8
0x180002bf6  mov     [rsp+98h+var_78], r11d
0x180002bfb  mov     rcx, [rcx+10h]
0x180002bff  lea     r9, aHr; "hr"
0x180002c06  call    WPP_SF_sDsd
0x180002c0b  jmp     loc_180002B81
0x180002c10  mov     ebx, 80090026h
0x180002c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c1c  lea     rax, WPP_GLOBAL_Control
0x180002c23  cmp     rcx, rax
0x180002c26  jz      loc_180002904
0x180002c2c  test    byte ptr [rcx+1Ch], 1
0x180002c30  jz      loc_180002904
0x180002c36  mov     dword ptr [rsp+98h+var_68], 3BAh
0x180002c3e  jmp     loc_180002856
0x180002c43  test    byte ptr [rcx+1Ch], 1
0x180002c47  jz      loc_180002A08
0x180002c4d  mov     dword ptr [rsp+98h+var_68], 402h
0x180002c55  jmp     loc_180002A60
0x180002c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c61  lea     rax, WPP_GLOBAL_Control
0x180002c68  cmp     rcx, rax
0x180002c6b  jz      loc_180002B81
0x180002c71  test    byte ptr [rcx+1Ch], 1
0x180002c75  jz      loc_180002B81
0x180002c7b  mov     dword ptr [rsp+98h+var_68], 421h
0x180002c83  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002c8a  mov     [rsp+98h+var_70], r8
0x180002c8f  mov     [rsp+98h+var_78], edx
0x180002c93  jmp     loc_180002BFB
0x180002c98  mov     r9d, 43Dh
0x180002c9e  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002ca5  lea     rdx, aStatus; "Status"
0x180002cac  mov     ecx, 8009000Eh
0x180002cb1  mov     ebx, 8009000Eh
0x180002cb6  call    DebugTraceError
0x180002cbb  xor     r12d, r12d
0x180002cbe  jmp     loc_180002B86
0x180002cc3  mov     edx, 80070057h
0x180002cc8  jmp     short loc_180002C5A
0x180002cca  mov     [rsi], r15
0x180002ccd  mov     ebx, r12d
0x180002cd0  jmp     loc_180002904
0x180002cd5  mov     ebx, 80090020h
0x180002cda  mov     r9d, 451h
0x180002ce0  mov     ecx, 80090020h
0x180002ce5  jmp     short loc_180002CF7
0x180002ce7  mov     ebx, 80090027h
0x180002cec  mov     r9d, 3C1h
0x180002cf2  mov     ecx, 80090027h
0x180002cf7  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002cfe  lea     rdx, aStatus; "Status"
0x180002d05  call    DebugTraceError
0x180002d0a  jmp     loc_180002904
```
