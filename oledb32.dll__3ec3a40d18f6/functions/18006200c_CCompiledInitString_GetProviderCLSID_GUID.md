# CCompiledInitString::GetProviderCLSID(_GUID *)

- ea: `0x18006200c`
- end: `0x180062259`
- name: `?GetProviderCLSID@CCompiledInitString@@QEAAJPEAU_GUID@@@Z`
- size: `589`
- prototype: `int(CCompiledInitString *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028c78`

## callees

- `0x180013870`
- `0x180024af8`
- `0x180029560`
- `0x18002ec26`
- `0x18006200c`
- `0x18007e700`
- `0x18007e7c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180062142`
- `msvcrt!_wcsicmp` at `0x180062142`
- `ole32!CLSIDFromProgID` at `0x180062168`
- `ole32!CLSIDFromProgID` at `0x1800621ab`
- `ole32!CLSIDFromProgID` at `0x180062168`
- `ole32!CLSIDFromProgID` at `0x1800621ab`

## string_xrefs

- `0x1800620e9`: `<CCompiledInitString::GetProviderCLSID|OLEDB|ERR> `
- `0x1800621c7`: `<CCompiledInitString::GetProviderCLSID|OLEDB|ERR> `
- `0x18006220b`: `<CCompiledInitString::GetProviderCLSID|OLEDB|ERR> `
- `0x18006222f`: `<CCompiledInitString::GetProviderCLSID|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CCompiledInitString::GetProviderCLSID(CCompiledInitString *this, struct _GUID *a2)
{
  __int64 v2; // r9
  size_t v4; // rdx
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // r8
  void *v7; // rsp
  void *v8; // rsp
  const wchar_t *v9; // r8
  const wchar_t *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rbx
  struct stPROVIDERCLSID near **i; // rbx
  __int64 result; // rax
  __int64 v16; // rax
  wchar_t *v17; // rcx
  wchar_t pszDest[24]; // [rsp+30h] [rbp+0h] BYREF

  v2 = *((unsigned int *)this + 20);
  if ( (unsigned int)(v2 - 1) > 0xFA )
  {
    v11 = -2147221005;
    if ( (bidGblFlags & 2) == 0 )
      return v11;
    OLEDBTraceErr(-2147221005, L"<CCompiledInitString::GetProviderCLSID|OLEDB|ERR> ", 0x26Au);
    if ( (bidGblFlags & 2) == 0 )
      return v11;
    v12 = 632841;
    return (unsigned int)bidTraceHR(off_1800C8430[0], v12, L"<CCompiledInitString::GetProviderCLSID|Trace|HR> ", v11);
  }
  v4 = (unsigned int)(v2 + 1);
  v5 = 2 * v4 + 15;
  if ( v5 < 2 * v4 )
    v5 = 0xFFFFFFFFFFFFFF0LL;
  v6 = v5 & 0xFFFFFFFFFFFFFFF0uLL;
  v7 = alloca(v6);
  v8 = alloca(v6);
  v9 = (const wchar_t *)*((_QWORD *)this + 9);
  if ( *v9 == 34 || *v9 == 39 )
  {
    v10 = &v9[v2 - 1];
    if ( *v10 != 34 && *v10 != 39 )
    {
      v11 = -2147221005;
      if ( (bidGblFlags & 2) == 0 )
        return v11;
      OLEDBTraceErr(-2147221005, L"<CCompiledInitString::GetProviderCLSID|OLEDB|ERR> ", 0x277u);
      if ( (bidGblFlags & 2) == 0 )
        return v11;
      v12 = 646153;
      return (unsigned int)bidTraceHR(off_1800C8430[0], v12, L"<CCompiledInitString::GetProviderCLSID|Trace|HR> ", v11);
    }
    v13 = (unsigned int)((2 * (v2 - 1) - 2) >> 1);
    memcpy_0(pszDest, v9 + 1, v13 * 2);
    pszDest[v13] = 0;
  }
  else if ( (_DWORD)v2 != -1 )
  {
    if ( v4 > 0x7FFFFFFF || (unsigned int)v2 > 0x7FFFFFFE )
      pszDest[0] = 0;
    else
      StringCopyWorkerW_0(pszDest, v4, 0, v9, *((unsigned int *)this + 20));
  }
  for ( i = &g_rgProviderClsid; *i; i += 2 )
  {
    if ( !_wcsicmp(pszDest, (const wchar_t *)*i) )
    {
      result = 0;
      *a2 = *(struct _GUID *)i[1];
      return result;
    }
  }
  v11 = CLSIDFromProgID(pszDest, a2);
  if ( (v11 & 0x80000000) != 0 )
  {
    v16 = -1;
    do
      ++v16;
    while ( pszDest[v16] );
    v17 = &pszDest[v16];
    if ( 2 * v16 )
    {
      while ( *v17 != 46 )
      {
        if ( --v17 == pszDest )
          goto LABEL_28;
      }
    }
    else
    {
LABEL_28:
      if ( *v17 != 46 )
        goto LABEL_33;
    }
    *v17 = 0;
    v11 = CLSIDFromProgID(pszDest, a2);
    if ( (v11 & 0x80000000) != 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v11;
      OLEDBTraceErr(v11, L"<CCompiledInitString::GetProviderCLSID|OLEDB|ERR> ", 0x29Bu);
      if ( (bidGblFlags & 2) == 0 )
        return v11;
      v12 = 683017;
      return (unsigned int)bidTraceHR(off_1800C8430[0], v12, L"<CCompiledInitString::GetProviderCLSID|Trace|HR> ", v11);
    }
  }
LABEL_33:
  if ( (bidGblFlags & 2) != 0 )
  {
    v12 = 687113;
    return (unsigned int)bidTraceHR(off_1800C8430[0], v12, L"<CCompiledInitString::GetProviderCLSID|Trace|HR> ", v11);
  }
  return v11;
}

```

## disassembly

```asm
0x18006200c  push    rbp
0x18006200e  push    rbx
0x18006200f  push    rsi
0x180062010  push    rdi
0x180062011  push    r14
0x180062013  sub     rsp, 40h
0x180062017  lea     rbp, [rsp+30h]
0x18006201c  mov     rax, cs:__security_cookie
0x180062023  xor     rax, rbp
0x180062026  mov     qword ptr [rbp+30h+pszDest], rax
0x18006202a  mov     r9d, [rcx+50h]
0x18006202e  mov     r14, rdx
0x180062031  lea     eax, [r9-1]
0x180062035  cmp     eax, 0FAh
0x18006203a  ja      loc_1800621F6
0x180062040  lea     eax, [r9+1]
0x180062044  mov     edx, eax
0x180062046  add     rax, rax
0x180062049  lea     r8, [rax+0Fh]
0x18006204d  cmp     r8, rax
0x180062050  ja      short loc_18006205C
0x180062052  mov     r8, 0FFFFFFFFFFFFFF0h
0x18006205c  and     r8, 0FFFFFFFFFFFFFFF0h
0x180062060  mov     rax, r8
0x180062063  call    _alloca_probe
0x180062068  sub     rsp, r8
0x18006206b  mov     r8, [rcx+48h]
0x18006206f  cmp     word ptr [r8], 22h ; '"'
0x180062074  lea     rsi, [rsp+60h+pszDest]
0x180062079  jz      short loc_1800620BC
0x18006207b  cmp     word ptr [r8], 27h ; '''
0x180062080  jz      short loc_1800620BC
0x180062082  xor     edi, edi
0x180062084  test    rdx, rdx
0x180062087  jz      loc_180062130
0x18006208d  cmp     rdx, 7FFFFFFFh
0x180062094  jbe     short loc_18006209E
0x180062096  mov     [rsi], di
0x180062099  jmp     loc_180062130
0x18006209e  cmp     r9d, 7FFFFFFEh
0x1800620a5  ja      short loc_180062096
0x1800620a7  mov     [rsp+60h+cchToCopy], r9; cchToCopy
0x1800620ac  mov     rcx, rsi; pszDest
0x1800620af  mov     r9, r8; pszSrc
0x1800620b2  xor     r8d, r8d; pcchNewDestLength
0x1800620b5  call    StringCopyWorkerW_0
0x1800620ba  jmp     short loc_180062130
0x1800620bc  lea     rcx, [r9-1]
0x1800620c0  lea     rcx, [r8+rcx*2]
0x1800620c4  cmp     word ptr [rcx], 22h ; '"'
0x1800620c8  jz      short loc_18006210F
0x1800620ca  cmp     word ptr [rcx], 27h ; '''
0x1800620ce  jz      short loc_18006210F
0x1800620d0  mov     eax, cs:_bidGblFlags
0x1800620d6  mov     ebx, 800401F3h
0x1800620db  test    al, 2
0x1800620dd  jz      loc_180062240
0x1800620e3  mov     r8d, 277h; unsigned int
0x1800620e9  lea     rdx, aCcompiledinits_1; "<CCompiledInitString::GetProviderCLSID|"...
0x1800620f0  mov     ecx, ebx; int
0x1800620f2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800620f7  mov     eax, cs:_bidGblFlags
0x1800620fd  test    al, 2
0x1800620ff  jz      loc_180062240
0x180062105  mov     edx, 9DC09h
0x18006210a  jmp     loc_180062228
0x18006210f  lea     rdx, [r8+2]; Src
0x180062113  sub     rcx, rdx
0x180062116  sar     rcx, 1
0x180062119  mov     eax, ecx
0x18006211b  mov     rcx, rsi; void *
0x18006211e  lea     rbx, [rax+rax]
0x180062122  mov     r8, rbx; Size
0x180062125  call    memcpy_0
0x18006212a  xor     edi, edi
0x18006212c  mov     [rbx+rsi], di
0x180062130  lea     rbx, ?g_rgProviderClsid@@3PAUstPROVIDERCLSID@@A; stPROVIDERCLSID near * g_rgProviderClsid
0x180062137  mov     rcx, rsi; lpszProgID
0x18006213a  cmp     [rbx], rdi
0x18006213d  jz      short loc_180062165
0x18006213f  mov     rdx, [rbx]; String2
0x180062142  call    cs:__imp__wcsicmp
0x180062148  test    eax, eax
0x18006214a  jz      short loc_180062152
0x18006214c  add     rbx, 10h
0x180062150  jmp     short loc_180062137
0x180062152  mov     rax, [rbx+8]
0x180062156  movups  xmm0, xmmword ptr [rax]
0x180062159  xor     eax, eax
0x18006215b  movdqu  xmmword ptr [r14], xmm0
0x180062160  jmp     loc_180062242
0x180062165  mov     rdx, r14; lpclsid
0x180062168  call    cs:__imp_CLSIDFromProgID
0x18006216e  mov     ebx, eax
0x180062170  test    eax, eax
0x180062172  jns     short loc_1800621E6
0x180062174  or      rax, 0FFFFFFFFFFFFFFFFh
0x180062178  inc     rax
0x18006217b  cmp     [rsi+rax*2], di
0x18006217f  jnz     short loc_180062178
0x180062181  add     rax, rax
0x180062184  mov     edx, 2Eh ; '.'
0x180062189  lea     rcx, [rax+rsi]
0x18006218d  jz      short loc_18006219D
0x18006218f  cmp     dx, [rcx]
0x180062192  jz      short loc_1800621A2
0x180062194  sub     rcx, 2
0x180062198  cmp     rcx, rsi
0x18006219b  jnz     short loc_18006218F
0x18006219d  cmp     dx, [rcx]
0x1800621a0  jnz     short loc_1800621E6
0x1800621a2  mov     [rcx], di
0x1800621a5  mov     rdx, r14; lpclsid
0x1800621a8  mov     rcx, rsi; lpszProgID
0x1800621ab  call    cs:__imp_CLSIDFromProgID
0x1800621b1  mov     ebx, eax
0x1800621b3  test    eax, eax
0x1800621b5  jns     short loc_1800621E6
0x1800621b7  mov     eax, cs:_bidGblFlags
0x1800621bd  test    al, 2
0x1800621bf  jz      short loc_180062240
0x1800621c1  mov     r8d, 29Bh; unsigned int
0x1800621c7  lea     rdx, aCcompiledinits_1; "<CCompiledInitString::GetProviderCLSID|"...
0x1800621ce  mov     ecx, ebx; int
0x1800621d0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800621d5  mov     eax, cs:_bidGblFlags
0x1800621db  test    al, 2
0x1800621dd  jz      short loc_180062240
0x1800621df  mov     edx, 0A6C09h
0x1800621e4  jmp     short loc_180062228
0x1800621e6  test    byte ptr cs:_bidGblFlags, 2
0x1800621ed  jz      short loc_180062240
0x1800621ef  mov     edx, 0A7C09h
0x1800621f4  jmp     short loc_180062228
0x1800621f6  mov     eax, cs:_bidGblFlags
0x1800621fc  mov     ebx, 800401F3h
0x180062201  test    al, 2
0x180062203  jz      short loc_180062240
0x180062205  mov     r8d, 26Ah; unsigned int
0x18006220b  lea     rdx, aCcompiledinits_1; "<CCompiledInitString::GetProviderCLSID|"...
0x180062212  mov     ecx, ebx; int
0x180062214  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180062219  mov     eax, cs:_bidGblFlags
0x18006221f  test    al, 2
0x180062221  jz      short loc_180062240
0x180062223  mov     edx, 9A809h
0x180062228  mov     rcx, cs:off_1800C8430; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006222f  lea     r8, aCcompiledinits; "<CCompiledInitString::GetProviderCLSID|"...
0x180062236  mov     r9d, ebx
0x180062239  call    _bidTraceHR
0x18006223e  mov     ebx, eax
0x180062240  mov     eax, ebx
0x180062242  mov     rcx, qword ptr [rbp+30h+pszDest]
0x180062246  xor     rcx, rbp; StackCookie
0x180062249  call    __security_check_cookie
0x18006224e  lea     rsp, [rbp+10h]
0x180062252  pop     r14
0x180062254  pop     rdi
0x180062255  pop     rsi
0x180062256  pop     rbx
0x180062257  pop     rbp
0x180062258  retn
```
