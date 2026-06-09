# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180028180`
- end: `0x1800283e4`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180028d8c`

## callees

- `0x18001e1e0`
- `0x1800238f8`
- `0x180025548`
- `0x18002579c`
- `0x180027e3c`
- `0x180028180`
- `0x180029f0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800282ba`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800282ba`
- `USER32!CharNextW` at `0x180028250`
- `USER32!CharNextW` at `0x18002835f`
- `USER32!CharNextW` at `0x180028375`
- `USER32!CharNextW` at `0x180028250`
- `USER32!CharNextW` at `0x18002835f`
- `USER32!CharNextW` at `0x180028375`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002831b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002831b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800282d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800282d2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800282f3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800282f3`
- `ole32!CoTaskMemFree` at `0x180028222`
- `ole32!CoTaskMemFree` at `0x1800283ae`
- `ole32!CoTaskMemFree` at `0x180028222`
- `ole32!CoTaskMemFree` at `0x1800283ae`
- `ole32!CoTaskMemAlloc` at `0x180028207`
- `ole32!CoTaskMemAlloc` at `0x180028207`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
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
  LODWORD(v27) = 0;
  HIDWORD(v27) = v7;
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
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *(_QWORD *)this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, v27);
    ATL::AtlCrtErrorCheck(v17);
    v18 = *((_QWORD *)this + 1);
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
    v20 = v18 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v20 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), String2) )
      {
        if ( i != -1 )
        {
          v22 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v20,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v22 = 0;
LABEL_29:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_39:
      v13 = -2147352567;
      goto LABEL_41;
    }
    v29 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v15; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x180028180  mov     [rsp-8+arg_8], rbx
0x180028185  push    rbp
0x180028186  push    rsi
0x180028187  push    rdi
0x180028188  push    r12
0x18002818a  push    r13
0x18002818c  push    r14
0x18002818e  push    r15
0x180028190  lea     rbp, [rsp-27h]
0x180028195  sub     rsp, 90h
0x18002819c  mov     rax, cs:__security_cookie
0x1800281a3  xor     rax, rsp
0x1800281a6  mov     [rbp+57h+var_40], rax
0x1800281aa  mov     r15, r8
0x1800281ad  mov     rbx, rdx
0x1800281b0  mov     rdi, rcx
0x1800281b3  xor     r13d, r13d
0x1800281b6  test    rdx, rdx
0x1800281b9  jz      loc_1800283B8
0x1800281bf  test    r8, r8
0x1800281c2  jz      loc_1800283B8
0x1800281c8  mov     [r8], r13
0x1800281cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800281cf  inc     rax
0x1800281d2  cmp     [rdx+rax*2], r13w
0x1800281d7  jnz     short loc_1800281CF
0x1800281d9  add     eax, eax
0x1800281db  mov     ecx, 3E8h
0x1800281e0  cmp     eax, 64h ; 'd'
0x1800281e3  cmovl   eax, ecx
0x1800281e6  mov     [rbp+57h+var_A0], r13d
0x1800281ea  mov     [rbp+57h+var_9C], eax
0x1800281ed  mov     ecx, eax
0x1800281ef  add     rcx, rcx
0x1800281f2  mov     eax, 0FFFFFFFFh
0x1800281f7  cmp     rcx, rax
0x1800281fa  jbe     short loc_180028205
0x1800281fc  mov     rax, r13
0x1800281ff  mov     [rbp+57h+pv], r13
0x180028203  jmp     short loc_18002821A
0x180028205  mov     ecx, ecx; cb
0x180028207  call    cs:__imp_CoTaskMemAlloc
0x18002820d  mov     [rbp+57h+pv], rax
0x180028211  test    rax, rax
0x180028214  jz      short loc_18002821A
0x180028216  mov     [rax], r13w
0x18002821a  test    rax, rax
0x18002821d  jnz     short loc_180028232
0x18002821f  mov     rcx, rax; pv
0x180028222  call    cs:__imp_CoTaskMemFree
0x180028228  mov     eax, 8007000Eh
0x18002822d  jmp     loc_1800283BD
0x180028232  mov     [rdi], rbx
0x180028235  mov     esi, 25h ; '%'
0x18002823a  cmp     [rbx], r13w
0x18002823e  jz      loc_18002839C
0x180028244  cmp     [rbx], si
0x180028247  jnz     loc_180028386
0x18002824d  mov     rcx, rbx; lpsz
0x180028250  call    cs:__imp_CharNextW
0x180028256  mov     [rdi], rax
0x180028259  cmp     [rax], si
0x18002825c  jnz     short loc_180028282
0x18002825e  mov     rdx, rax; unsigned __int16 *
0x180028261  mov     r8d, 1; int
0x180028267  lea     rcx, [rbp+57h+var_A0]; this
0x18002826b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180028270  test    eax, eax
0x180028272  jnz     loc_180028372
0x180028278  mov     ebx, 8007000Eh
0x18002827d  jmp     loc_1800283AA
0x180028282  mov     edx, esi; unsigned __int16
0x180028284  mov     rcx, rax; lpsz
0x180028287  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002828c  mov     rsi, rax
0x18002828f  test    rax, rax
0x180028292  jz      loc_180028395
0x180028298  mov     rcx, rax
0x18002829b  sub     rcx, [rdi]
0x18002829e  sar     rcx, 1
0x1800282a1  cmp     rcx, 1Fh
0x1800282a5  jg      loc_18002838E
0x1800282ab  movsxd  r9, ecx
0x1800282ae  mov     r8, [rdi]
0x1800282b1  mov     edx, 20h ; ' '
0x1800282b6  lea     rcx, [rbp+57h+String2]
0x1800282ba  call    cs:__imp__o_wcsncpy_s
0x1800282c0  mov     ecx, eax; int
0x1800282c2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800282c7  mov     rbx, [rdi+8]
0x1800282cb  lea     r12, [rbx+20h]
0x1800282cf  mov     rcx, r12; lpCriticalSection
0x1800282d2  call    cs:__imp_EnterCriticalSection
0x1800282d8  lea     r14, [rbx+8]
0x1800282dc  mov     ebx, r13d
0x1800282df  cmp     ebx, [r14+10h]
0x1800282e3  jge     short loc_180028315
0x1800282e5  movsxd  rax, ebx
0x1800282e8  mov     rcx, [r14]
0x1800282eb  lea     rdx, [rbp+57h+String2]; lpString2
0x1800282ef  mov     rcx, [rcx+rax*8]; lpString1
0x1800282f3  call    cs:__imp_lstrcmpiW
0x1800282f9  test    eax, eax
0x1800282fb  jz      short loc_180028301
0x1800282fd  inc     ebx
0x1800282ff  jmp     short loc_1800282DF
0x180028301  cmp     ebx, 0FFFFFFFFh
0x180028304  jz      short loc_180028315
0x180028306  mov     edx, ebx
0x180028308  mov     rcx, r14
0x18002830b  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180028310  mov     rbx, [rax]
0x180028313  jmp     short loc_180028318
0x180028315  mov     rbx, r13
0x180028318  mov     rcx, r12; lpCriticalSection
0x18002831b  call    cs:__imp_LeaveCriticalSection
0x180028321  test    rbx, rbx
0x180028324  jz      short loc_180028395
0x180028326  mov     [rbp+57h+var_90], r13
0x18002832a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002832e  inc     r8; int
0x180028331  cmp     [rbx+r8*2], r13w
0x180028336  jnz     short loc_18002832E
0x180028338  mov     rdx, rbx; unsigned __int16 *
0x18002833b  lea     rcx, [rbp+57h+var_A0]; this
0x18002833f  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180028344  mov     ebx, eax
0x180028346  lea     rcx, [rbp+57h+var_90]
0x18002834a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002834f  test    ebx, ebx
0x180028351  jz      loc_180028278
0x180028357  mov     rax, [rdi]
0x18002835a  jmp     short loc_180028368
0x18002835c  mov     rcx, rax; lpsz
0x18002835f  call    cs:__imp_CharNextW
0x180028365  mov     [rdi], rax
0x180028368  cmp     rax, rsi
0x18002836b  jnz     short loc_18002835C
0x18002836d  mov     esi, 25h ; '%'
0x180028372  mov     rcx, [rdi]; lpsz
0x180028375  call    cs:__imp_CharNextW
0x18002837b  mov     rbx, rax
0x18002837e  mov     [rdi], rax
0x180028381  jmp     loc_18002823A
0x180028386  mov     rdx, rbx
0x180028389  jmp     loc_180028261
0x18002838e  mov     ebx, 80004005h
0x180028393  jmp     short loc_1800283AA
0x180028395  mov     ebx, 80020009h
0x18002839a  jmp     short loc_1800283AA
0x18002839c  mov     ebx, r13d
0x18002839f  mov     rcx, [rbp+57h+pv]
0x1800283a3  mov     [rbp+57h+pv], r13
0x1800283a7  mov     [r15], rcx
0x1800283aa  mov     rcx, [rbp+57h+pv]; pv
0x1800283ae  call    cs:__imp_CoTaskMemFree
0x1800283b4  mov     eax, ebx
0x1800283b6  jmp     short loc_1800283BD
0x1800283b8  mov     eax, 80004003h
0x1800283bd  mov     rcx, [rbp+57h+var_40]
0x1800283c1  xor     rcx, rsp; StackCookie
0x1800283c4  call    __security_check_cookie
0x1800283c9  mov     rbx, [rsp+0C0h+arg_8]
0x1800283d1  add     rsp, 90h
0x1800283d8  pop     r15
0x1800283da  pop     r14
0x1800283dc  pop     r13
0x1800283de  pop     r12
0x1800283e0  pop     rdi
0x1800283e1  pop     rsi
0x1800283e2  pop     rbp
0x1800283e3  retn
```
