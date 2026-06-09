# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800223b8`
- end: `0x1800225fa`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `578`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800227ac`

## callees

- `0x18001e4c0`
- `0x1800206d0`
- `0x1800211ec`
- `0x18002132c`
- `0x180021d9c`
- `0x1800223b8`
- `0x180023258`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800224da`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800224da`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002248a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180022563`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002258c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002248a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180022563`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002258c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022507`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022507`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002245a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800225c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002245a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800225c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002243f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002243f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  LPCWSTR v17; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v19; // rdx
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *j; // rax
  unsigned int v23; // ebx
  unsigned __int16 *v24; // rcx
  __int64 v25; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

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
  LODWORD(v25) = 0;
  HIDWORD(v25) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  for ( *this = v4; ; *this = v4 )
  {
    if ( !*v4 )
    {
      v23 = 0;
      v24 = (unsigned __int16 *)pv;
      pv = 0;
      *a3 = v24;
      goto LABEL_40;
    }
    if ( *v4 == 37 )
      break;
    v12 = v4;
LABEL_34:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v12, 1) )
    {
LABEL_38:
      v23 = -2147024882;
      goto LABEL_40;
    }
LABEL_35:
    v4 = CharNextW(*this);
  }
  v11 = CharNextW(v4);
  *this = v11;
  if ( *v11 == 37 )
  {
    v12 = v11;
    goto LABEL_34;
  }
  v13 = ATL::CRegParser::StrChrW(v11, 0x25u);
  v14 = v13;
  if ( v13 )
  {
    v15 = v13 - *this;
    if ( v15 > 31 )
    {
      v23 = -2147467259;
      goto LABEL_40;
    }
    v16 = _o_wcsncpy_s(String2, 32, *this, (int)v15, v25);
    ATL::AtlCrtErrorCheck(v16);
    v17 = this[1];
    for ( i = 0; (signed int)i < *((_DWORD *)v17 + 6); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v17 + 1) + 8LL * (int)i), String2) )
      {
        if ( i == -1 )
          break;
        v19 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                            v17 + 4,
                                            i);
        if ( !v19 )
          break;
        v27 = 0;
        v20 = -1;
        do
          ++v20;
        while ( v19[v20] );
        v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v19, v20);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v27);
        if ( v21 )
        {
          for ( j = *this; j != v14; *this = j )
            j = CharNextW(j);
          goto LABEL_35;
        }
        goto LABEL_38;
      }
    }
  }
  v23 = -2147352567;
LABEL_40:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x1800223b8  mov     [rsp-8+arg_8], rbx
0x1800223bd  push    rbp
0x1800223be  push    rsi
0x1800223bf  push    rdi
0x1800223c0  push    r12
0x1800223c2  push    r13
0x1800223c4  push    r14
0x1800223c6  push    r15
0x1800223c8  lea     rbp, [rsp-27h]
0x1800223cd  sub     rsp, 90h
0x1800223d4  mov     rax, cs:__security_cookie
0x1800223db  xor     rax, rsp
0x1800223de  mov     [rbp+57h+var_40], rax
0x1800223e2  mov     r15, r8
0x1800223e5  mov     rbx, rdx
0x1800223e8  mov     rdi, rcx
0x1800223eb  xor     r12d, r12d
0x1800223ee  test    rdx, rdx
0x1800223f1  jz      loc_1800225CE
0x1800223f7  test    r8, r8
0x1800223fa  jz      loc_1800225CE
0x180022400  mov     [r8], r12
0x180022403  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022407  inc     rax
0x18002240a  cmp     [rdx+rax*2], r12w
0x18002240f  jnz     short loc_180022407
0x180022411  add     eax, eax
0x180022413  mov     ecx, 3E8h
0x180022418  cmp     eax, 64h ; 'd'
0x18002241b  cmovl   eax, ecx
0x18002241e  mov     [rbp+57h+var_A0], r12d
0x180022422  mov     [rbp+57h+var_9C], eax
0x180022425  mov     ecx, eax
0x180022427  add     rcx, rcx
0x18002242a  mov     eax, 0FFFFFFFFh
0x18002242f  cmp     rcx, rax
0x180022432  jbe     short loc_18002243D
0x180022434  mov     rax, r12
0x180022437  mov     [rbp+57h+pv], r12
0x18002243b  jmp     short loc_180022452
0x18002243d  mov     ecx, ecx; cb
0x18002243f  call    cs:__imp_CoTaskMemAlloc
0x180022445  mov     [rbp+57h+pv], rax
0x180022449  test    rax, rax
0x18002244c  jz      short loc_180022452
0x18002244e  mov     [rax], r12w
0x180022452  test    rax, rax
0x180022455  jnz     short loc_18002246A
0x180022457  mov     rcx, rax; pv
0x18002245a  call    cs:__imp_CoTaskMemFree
0x180022460  mov     eax, 8007000Eh
0x180022465  jmp     loc_1800225D3
0x18002246a  mov     [rdi], rbx
0x18002246d  mov     r13d, 25h ; '%'
0x180022473  cmp     [rbx], r12w
0x180022477  jz      loc_1800225B2
0x18002247d  cmp     [rbx], r13w
0x180022481  jnz     loc_180022573
0x180022487  mov     rcx, rbx; lpsz
0x18002248a  call    cs:__imp_CharNextW
0x180022490  mov     [rdi], rax
0x180022493  cmp     [rax], r13w
0x180022497  jnz     short loc_1800224A1
0x180022499  mov     rdx, rax
0x18002249c  jmp     loc_180022576
0x1800224a1  mov     edx, r13d; unsigned __int16
0x1800224a4  mov     rcx, rax; lpsz
0x1800224a7  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800224ac  mov     rsi, rax
0x1800224af  test    rax, rax
0x1800224b2  jz      loc_1800225A4
0x1800224b8  mov     rcx, rax
0x1800224bb  sub     rcx, [rdi]
0x1800224be  sar     rcx, 1
0x1800224c1  cmp     rcx, 1Fh
0x1800224c5  jg      loc_18002259D
0x1800224cb  movsxd  r9, ecx
0x1800224ce  mov     r8, [rdi]
0x1800224d1  mov     edx, 20h ; ' '
0x1800224d6  lea     rcx, [rbp+57h+String2]
0x1800224da  call    cs:__imp__o_wcsncpy_s
0x1800224e0  mov     ecx, eax; int
0x1800224e2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800224e7  mov     r14, [rdi+8]
0x1800224eb  mov     ebx, r12d
0x1800224ee  cmp     ebx, [r14+18h]
0x1800224f2  jge     loc_1800225A4
0x1800224f8  movsxd  rax, ebx
0x1800224fb  mov     rcx, [r14+8]
0x1800224ff  lea     rdx, [rbp+57h+String2]; lpString2
0x180022503  mov     rcx, [rcx+rax*8]; lpString1
0x180022507  call    cs:__imp_lstrcmpiW
0x18002250d  test    eax, eax
0x18002250f  jz      short loc_180022515
0x180022511  inc     ebx
0x180022513  jmp     short loc_1800224EE
0x180022515  cmp     ebx, 0FFFFFFFFh
0x180022518  jz      loc_1800225A4
0x18002251e  mov     edx, ebx
0x180022520  lea     rcx, [r14+8]
0x180022524  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180022529  mov     rdx, [rax]; unsigned __int16 *
0x18002252c  test    rdx, rdx
0x18002252f  jz      short loc_1800225A4
0x180022531  mov     [rbp+57h+var_90], r12
0x180022535  or      r8, 0FFFFFFFFFFFFFFFFh
0x180022539  inc     r8; int
0x18002253c  cmp     [rdx+r8*2], r12w
0x180022541  jnz     short loc_180022539
0x180022543  lea     rcx, [rbp+57h+var_A0]; this
0x180022547  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18002254c  mov     ebx, eax
0x18002254e  lea     rcx, [rbp+57h+var_90]
0x180022552  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180022557  test    ebx, ebx
0x180022559  jz      short loc_1800225AB
0x18002255b  mov     rax, [rdi]
0x18002255e  jmp     short loc_18002256C
0x180022560  mov     rcx, rax; lpsz
0x180022563  call    cs:__imp_CharNextW
0x180022569  mov     [rdi], rax
0x18002256c  cmp     rax, rsi
0x18002256f  jnz     short loc_180022560
0x180022571  jmp     short loc_180022589
0x180022573  mov     rdx, rbx; unsigned __int16 *
0x180022576  mov     r8d, 1; int
0x18002257c  lea     rcx, [rbp+57h+var_A0]; this
0x180022580  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180022585  test    eax, eax
0x180022587  jz      short loc_1800225AB
0x180022589  mov     rcx, [rdi]; lpsz
0x18002258c  call    cs:__imp_CharNextW
0x180022592  mov     rbx, rax
0x180022595  mov     [rdi], rax
0x180022598  jmp     loc_180022473
0x18002259d  mov     ebx, 80004005h
0x1800225a2  jmp     short loc_1800225C0
0x1800225a4  mov     ebx, 80020009h
0x1800225a9  jmp     short loc_1800225C0
0x1800225ab  mov     ebx, 8007000Eh
0x1800225b0  jmp     short loc_1800225C0
0x1800225b2  mov     ebx, r12d
0x1800225b5  mov     rcx, [rbp+57h+pv]
0x1800225b9  mov     [rbp+57h+pv], r12
0x1800225bd  mov     [r15], rcx
0x1800225c0  mov     rcx, [rbp+57h+pv]; pv
0x1800225c4  call    cs:__imp_CoTaskMemFree
0x1800225ca  mov     eax, ebx
0x1800225cc  jmp     short loc_1800225D3
0x1800225ce  mov     eax, 80004003h
0x1800225d3  mov     rcx, [rbp+57h+var_40]
0x1800225d7  xor     rcx, rsp; StackCookie
0x1800225da  call    __security_check_cookie
0x1800225df  mov     rbx, [rsp+0C0h+arg_8]
0x1800225e7  add     rsp, 90h
0x1800225ee  pop     r15
0x1800225f0  pop     r14
0x1800225f2  pop     r13
0x1800225f4  pop     r12
0x1800225f6  pop     rdi
0x1800225f7  pop     rsi
0x1800225f8  pop     rbp
0x1800225f9  retn
```
