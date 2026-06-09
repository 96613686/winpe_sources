# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180053254`
- end: `0x180053477`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `547`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800536a0`

## callees

- `0x18004e0c0`
- `0x18005021c`
- `0x180050cdc`
- `0x180050e10`
- `0x180053254`
- `0x180054ab8`
- `0x180054b10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180053380`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180053380`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180053330`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800533d8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180053401`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180053330`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800533d8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180053401`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800532fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005342b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800532fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005342b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800532e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800532e0`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // rcx
  int v18; // eax
  const unsigned __int16 *v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  __int64 v24; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 v27[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(v24) = 0;
  HIDWORD(v24) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_31:
    v23 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_32;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_28:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v24, v14, 1) )
      goto LABEL_35;
LABEL_29:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_31;
    }
  }
  v13 = CharNextW(v4);
  *(_QWORD *)this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_28;
  }
  v15 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_34;
  v17 = ((__int64)v15 - *(_QWORD *)this) >> 1;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_32;
  }
  v18 = _o_wcsncpy_s(v27, 32, *(_QWORD *)this, (int)v17, v24);
  ATL::AtlCrtErrorCheck(v18);
  v19 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), v27);
  if ( !v19 )
  {
LABEL_34:
    v23 = -2147352567;
    goto LABEL_32;
  }
  v26 = 0;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v24, v19, v20);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v26);
  if ( v21 )
  {
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
    goto LABEL_29;
  }
LABEL_35:
  v23 = -2147024882;
LABEL_32:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x180053254  mov     [rsp-8+arg_8], rbx
0x180053259  mov     [rsp-8+arg_18], rsi
0x18005325e  push    rbp
0x18005325f  push    rdi
0x180053260  push    r12
0x180053262  push    r14
0x180053264  push    r15
0x180053266  lea     rbp, [rsp-37h]
0x18005326b  sub     rsp, 90h
0x180053272  mov     rax, cs:__security_cookie
0x180053279  xor     rax, rsp
0x18005327c  mov     [rbp+57h+var_30], rax
0x180053280  mov     r14, r8
0x180053283  mov     rbx, rdx
0x180053286  mov     rdi, rcx
0x180053289  xor     r15d, r15d
0x18005328c  test    rdx, rdx
0x18005328f  jz      loc_18005344A
0x180053295  test    r8, r8
0x180053298  jz      loc_18005344A
0x18005329e  mov     [r8], r15
0x1800532a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800532a5  inc     rax
0x1800532a8  cmp     [rdx+rax*2], r15w
0x1800532ad  jnz     short loc_1800532A5
0x1800532af  add     eax, eax
0x1800532b1  mov     ecx, 3E8h
0x1800532b6  cmp     eax, 64h ; 'd'
0x1800532b9  cmovl   eax, ecx
0x1800532bc  mov     [rbp+57h+var_90], r15d
0x1800532c0  mov     [rbp+57h+var_8C], eax
0x1800532c3  mov     ecx, eax
0x1800532c5  add     rcx, rcx
0x1800532c8  mov     eax, 0FFFFFFFFh
0x1800532cd  cmp     rcx, rax
0x1800532d0  jbe     short loc_1800532DE
0x1800532d2  mov     rax, r15
0x1800532d5  mov     rdx, r15
0x1800532d8  mov     [rbp+57h+pv], rdx
0x1800532dc  jmp     short loc_1800532F6
0x1800532de  mov     ecx, ecx; cb
0x1800532e0  call    cs:__imp_CoTaskMemAlloc
0x1800532e6  mov     rdx, rax
0x1800532e9  mov     [rbp+57h+pv], rax
0x1800532ed  test    rax, rax
0x1800532f0  jz      short loc_1800532F6
0x1800532f2  mov     [rax], r15w
0x1800532f6  test    rax, rax
0x1800532f9  jnz     short loc_18005330E
0x1800532fb  mov     rcx, rax; pv
0x1800532fe  call    cs:__imp_CoTaskMemFree
0x180053304  mov     eax, 8007000Eh
0x180053309  jmp     loc_18005344F
0x18005330e  mov     [rdi], rbx
0x180053311  movzx   eax, word ptr [rbx]
0x180053314  test    ax, ax
0x180053317  jz      loc_18005341D
0x18005331d  mov     r12d, 25h ; '%'
0x180053323  cmp     ax, r12w
0x180053327  jnz     loc_1800533E8
0x18005332d  mov     rcx, rbx; lpsz
0x180053330  call    cs:__imp_CharNextW
0x180053336  mov     [rdi], rax
0x180053339  cmp     [rax], r12w
0x18005333d  jnz     short loc_180053347
0x18005333f  mov     rdx, rax
0x180053342  jmp     loc_1800533EB
0x180053347  mov     edx, r12d; unsigned __int16
0x18005334a  mov     rcx, rax; lpsz
0x18005334d  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180053352  mov     rsi, rax
0x180053355  test    rax, rax
0x180053358  jz      loc_18005343C
0x18005335e  mov     rcx, rax
0x180053361  sub     rcx, [rdi]
0x180053364  sar     rcx, 1
0x180053367  cmp     rcx, 1Fh
0x18005336b  jg      loc_180053435
0x180053371  movsxd  r9, ecx
0x180053374  mov     r8, [rdi]
0x180053377  mov     edx, 20h ; ' '
0x18005337c  lea     rcx, [rbp+57h+var_70]
0x180053380  call    cs:__imp__o_wcsncpy_s
0x180053386  mov     ecx, eax; int
0x180053388  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18005338d  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180053391  mov     rcx, [rdi+8]; this
0x180053395  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x18005339a  test    rax, rax
0x18005339d  jz      loc_18005343C
0x1800533a3  mov     [rbp+57h+var_80], r15
0x1800533a7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800533ab  inc     r8; int
0x1800533ae  cmp     [rax+r8*2], r15w
0x1800533b3  jnz     short loc_1800533AB
0x1800533b5  mov     rdx, rax; unsigned __int16 *
0x1800533b8  lea     rcx, [rbp+57h+var_90]; this
0x1800533bc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800533c1  mov     ebx, eax
0x1800533c3  lea     rcx, [rbp+57h+var_80]
0x1800533c7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800533cc  test    ebx, ebx
0x1800533ce  jz      short loc_180053443
0x1800533d0  mov     rax, [rdi]
0x1800533d3  jmp     short loc_1800533E1
0x1800533d5  mov     rcx, rax; lpsz
0x1800533d8  call    cs:__imp_CharNextW
0x1800533de  mov     [rdi], rax
0x1800533e1  cmp     rax, rsi
0x1800533e4  jnz     short loc_1800533D5
0x1800533e6  jmp     short loc_1800533FE
0x1800533e8  mov     rdx, rbx; unsigned __int16 *
0x1800533eb  mov     r8d, 1; int
0x1800533f1  lea     rcx, [rbp+57h+var_90]; this
0x1800533f5  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800533fa  test    eax, eax
0x1800533fc  jz      short loc_180053443
0x1800533fe  mov     rcx, [rdi]; lpsz
0x180053401  call    cs:__imp_CharNextW
0x180053407  mov     rbx, rax
0x18005340a  mov     [rdi], rax
0x18005340d  movzx   eax, word ptr [rax]
0x180053410  test    ax, ax
0x180053413  jnz     loc_180053323
0x180053419  mov     rdx, [rbp+57h+pv]
0x18005341d  mov     ebx, r15d
0x180053420  mov     [rbp+57h+pv], r15
0x180053424  mov     [r14], rdx
0x180053427  mov     rcx, [rbp+57h+pv]; pv
0x18005342b  call    cs:__imp_CoTaskMemFree
0x180053431  mov     eax, ebx
0x180053433  jmp     short loc_18005344F
0x180053435  mov     ebx, 80004005h
0x18005343a  jmp     short loc_180053427
0x18005343c  mov     ebx, 80020009h
0x180053441  jmp     short loc_180053427
0x180053443  mov     ebx, 8007000Eh
0x180053448  jmp     short loc_180053427
0x18005344a  mov     eax, 80004003h
0x18005344f  mov     rcx, [rbp+57h+var_30]
0x180053453  xor     rcx, rsp; StackCookie
0x180053456  call    __security_check_cookie
0x18005345b  lea     r11, [rsp+0B0h+var_20]
0x180053463  mov     rbx, [r11+38h]
0x180053467  mov     rsi, [r11+48h]
0x18005346b  mov     rsp, r11
0x18005346e  pop     r15
0x180053470  pop     r14
0x180053472  pop     r12
0x180053474  pop     rdi
0x180053475  pop     rbp
0x180053476  retn
```
